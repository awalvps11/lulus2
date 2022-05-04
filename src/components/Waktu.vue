<template>
  <div class="row justify-content-center" id="pengumuman">
    <div class="col-md-6">
      <table
        class="table table-bordered mt-5 text-center rounded-4 shadow"
        id="table"
      >
        <thead class="bg-warning text-white">
          <tr>
            <th>
              <h1>{{ day }}</h1>
            </th>
            <th>
              <h1>{{ hour }}</h1>
            </th>
            <th>
              <h1>{{ minute }}</h1>
            </th>
            <th>
              <h1>{{ second }}</h1>
            </th>
          </tr>
        </thead>
        <tbody class="bg-dark text-white">
          <tr>
            <td>day</td>
            <td>hour</td>
            <td>minute</td>
            <td>second</td>
          </tr>
        </tbody>
      </table>
      <p class="text-sm-center fw-lighter fst-italic text-dark">
        Silahkan Menunggu
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps(["day", "hour", "minute", "second"]);
// import { ref } from "@vue/reactivity";
// import { onMounted } from "@vue/runtime-core";

// const countDownDate = ref(new Date("May 4, 2022 16:37:25").getTime());
// const now = ref(new Date().getTime());
// let jarak = ref(countDownDate.value - now.value);
// const day = ref(Math.floor(jarak.value / (1000 * 60 * 60 * 24)));
// const hour = ref(
//   Math.floor((jarak.value % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
// );
// const minute = ref(Math.floor((jarak.value % (1000 * 60 * 60)) / (1000 * 60)));
// const second = ref(Math.floor((jarak.value % (1000 * 60)) / 1000));

// onMounted(() => {
//   setInterval(() => {
//     now.value = new Date().getTime();
//     jarak.value = countDownDate.value - now.value;
//     day.value = Math.floor(jarak.value / (1000 * 60 * 60 * 24));
//     hour.value = Math.floor(
//       (jarak.value % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
//     );
//     minute.value = Math.floor((jarak.value % (1000 * 60 * 60)) / (1000 * 60));
//     second.value = Math.floor((jarak.value % (1000 * 60)) / 1000);
//   }, 1000);
// });
</script>
