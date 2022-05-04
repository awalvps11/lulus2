<template>
  <!-- Header - set the background image for the header in the line below-->
  <header
    class="py-5 bg-image-full"
    style="
      background-image: url('https://source.unsplash.com/1600x900/?nature,water');
    "
  >
    <div class="text-center my-5">
      <img
        class="img-fluid rounded-circle mb-4"
        :src="img2"
        alt="..."
        width="120"
      />
      <h1 class="text-warning fs-3 fw-bolder">SMAN 9 Luwu Utara</h1>
      <h3 class="text-primary mb-0 fw-bold">Pengumuman Kelulusan</h3>
    </div>
  </header>
</template>
<script setup>
import { ref } from "@vue/reactivity";

const img1 = ref("https://dummyimage.com/150x150/6c757d/dee2e6.jpg");
const img2 = ref(
  "https://3.bp.blogspot.com/-gN11Bm9bZwE/Vx4sIt0hy7I/AAAAAAAAPRo/X2c-dNo52Q8QLIWNjhj5LQwfot0KVTLqgCLcB/s1600/sulawesi%2Bselatan.png"
);
</script>
