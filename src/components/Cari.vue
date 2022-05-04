<template>
  <div class="row justify-content-center bg-light mt-5" id="pengumuman">
    <div class="col-md-8">
      <div class="input-group mb-3 mt-5">
        <input
          type="text"
          class="form-control"
          placeholder="Masukkan No Ujian Sekolah"
          v-model="cari"
          @focus="focus"
          required
        />
        <div class="input-group-append">
          <button
            class="btn btn-outline-warning ms-3"
            type="button"
            @click="carilah"
          >
            Cari
          </button>
        </div>
      </div>
      <div v-if="hidden == true">
        <div
          class="card mt-3 bg-warning text-white"
          v-for="(item, index) in post"
          :key="index"
        >
          <div class="card-body">
            <h5 class="card-title">{{ item.nama }}</h5>
            <p class="card-text">{{ item.harga }}</p>
          </div>
        </div>
      </div>
      <span v-if="show == true">
        <h2>Data Tidak Ditemukan</h2>
      </span>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "@vue/reactivity";

const cari = ref("");
const hidden = ref(false);
const show = ref(false);
const post = ref([]);
const time = ref(Date().toLocaleLowerCase());
const data = reactive({
  buah: [
    { id: 1, nama: "Apel", harga: 10000 },
    { id: 2, nama: "Jeruk", harga: 20000 },
    { id: 3, nama: "Mangga", harga: 30000 },
    { id: 4, nama: "Pisang", harga: 40000 },
    { id: 5, nama: "Semangka", harga: 50000 },
  ],
});
const carilah = () => {
  hidden.value = true;
  post.value = data.buah.filter((item) => {
    if (item.nama.toLowerCase() === cari.value.toLowerCase()) {
      return item.nama.toLowerCase().includes(cari.value.toLowerCase());
    }
  });
  if (post.value.length == 0) {
    show.value = true;
  }
};
const focus = () => {
  hidden.value = false;
  show.value = false;
};
</script>

<style scoop></style>
