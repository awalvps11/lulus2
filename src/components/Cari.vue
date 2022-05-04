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
          class="card mt-3 bg-info text-white"
          v-for="(item, index) in post"
          :key="index"
        >
          <div class="card-body">
            <h5 class="card-title">Nama: {{ item.nama }}</h5>
            <p class="card-text">Nis : {{ item.nis }}</p>
            <p class="card-text">Kelas :{{ item.kelas }}</p>
            <h2 class="card-text text-primary">Status : {{ item.ket }}</h2>
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
import db from "../db";

const cari = ref("");
const hidden = ref(false);
const show = ref(false);
const post = ref([]);
const time = ref(Date().toLocaleLowerCase());
const data = reactive(db);
const carilah = () => {
  hidden.value = true;
  data.filter((item) => {
    if (item.nis == cari.value) {
      post.value.push(item);
      show.value = false;
    }
  });
  if (post.value.length == 0) {
    show.value = true;
  }
};
const focus = () => {
  hidden.value = false;
  show.value = false;
  post.value = [];
};
</script>

<style scoop></style>
