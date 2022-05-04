<template>
  <div>
    <Navbar />
    <Header />
    <span class="mt-5">
      <Surat />
    </span>
    <div>
      <span v-if="day >= 0 && hour >= 0 && minute >= 0 && second >= 0">
        <Waktu :day="day" :hour="hour" :minute="minute" :second="second" />
      </span>
      <span v-else>
        <Cari />
      </span>
    </div>
    <span>
      <!-- <Content /> -->
    </span>
    <!-- <Element /> -->
    <Content2 />
    <Footer />
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import Header from "./components/Header.vue";
// import Content from "./components/Content.vue";
// import Element from "./components/Element.vue";
import Content2 from "./components/Content2.vue";
import Footer from "./components/Footer.vue";
import Waktu from "./components/Waktu.vue";
import Cari from "./components/Cari.vue";

import { ref } from "@vue/reactivity";
import { onMounted } from "@vue/runtime-core";
import Surat from "./components/Surat.vue";

const countDownDate = ref(new Date("May 4, 2022 21:35:25").getTime());
const now = ref(new Date().getTime());
let jarak = ref(countDownDate.value - now.value);
const day = ref(Math.floor(jarak.value / (1000 * 60 * 60 * 24)));
const hour = ref(
  Math.floor((jarak.value % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
);
const minute = ref(Math.floor((jarak.value % (1000 * 60 * 60)) / (1000 * 60)));
const second = ref(Math.floor((jarak.value % (1000 * 60)) / 1000));

onMounted(() => {
  setInterval(() => {
    now.value = new Date().getTime();
    jarak.value = countDownDate.value - now.value;
    day.value = Math.floor(jarak.value / (1000 * 60 * 60 * 24));
    hour.value = Math.floor(
      (jarak.value % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
    );
    minute.value = Math.floor((jarak.value % (1000 * 60 * 60)) / (1000 * 60));
    second.value = Math.floor((jarak.value % (1000 * 60)) / 1000);
  }, 1000);
});
</script>

<style></style>
