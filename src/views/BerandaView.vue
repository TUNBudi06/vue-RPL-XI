<script setup>
import { ref } from 'vue'

const tulisan = ref("Selamat datang di Pemrograman VueJS")
const nama = ref(null)

const inputName = ref("") // Add inputName ref to store the entered name

const submitName = () => {
  nama.value = inputName.value // Set nama to the entered name
}

const changeName = () => {
  // Implement logic to change the name here
  // For simplicity, it can just clear the nama
  nama.value = null
}

const angka1 = ref(0)
const angka2 = ref(0)
const hasilPerjumlahan = ref(0)

const jumlahkan = () => {
  hasilPerjumlahan.value = parseInt(angka1.value) + parseInt(angka2.value)
}

const perkalian = () => {
  hasilPerjumlahan.value = parseInt(angka1.value) * parseInt(angka2.value)
}
const pengurangan = () => {
  hasilPerjumlahan.value = parseInt(angka1.value) - parseInt(angka2.value)
}
const pembagian = () => {
  hasilPerjumlahan.value = parseInt(angka1.value) / parseInt(angka2.value)
}
const habisDibagi = () => {
  hasilPerjumlahan.value = parseInt(angka1.value) % parseInt(angka2.value)
}
</script>

<template>
  <div class="container">
    <h1 class="text-bg-info mb-4">{{ tulisan }}</h1>
    <h4 v-if="nama" class="mb-1">Nama programmer: {{ nama }} <button @click="changeName" class="btn btn-outline-secondary rounded btn-sm">change</button></h4>
    <div v-else>
      <input type="text" v-model="inputName" class="form-text me-2" placeholder="Enter your name">
      <button @click="submitName" class="btn btn-outline-info rounded btn-sm">Submit</button>
    </div>
    <div class="form">
      <label for="angka1" class="pe-2 form-label ">Masukkan angka1: </label>
      <input type="text" name="angka1" id="angka1" class="form-text rounded" v-model="angka1"><br>
    </div>

    <div>
      <label for="angka2" class="pe-2 form-label">Masukkan angka2: </label>
      <input type="text" name="angka2" class="form-text rounded" id="angka2" v-model="angka2"><br>
    </div>

    <div>
      <button type="button" class="btn btn-outline-primary btn-sm m-1" @click="jumlahkan">Jumlahkan</button>
      <button type="button" class="btn btn-outline-primary btn-sm m-1" @click="perkalian">perkalian</button>
      <button type="button" class="btn btn-outline-primary btn-sm m-1" @click="pembagian">pembagian</button>
      <button type="button" class="btn btn-outline-primary btn-sm m-1" @click="habisDibagi">habisDibagi</button>
      <button type="button" class="btn btn-outline-primary btn-sm m-1" @click="pengurangan">pengurangan</button>
    </div>

    <div>
      <label for="angka2">Hasil perjumlahan: </label> <p>{{ hasilPerjumlahan }}</p>
    </div>
  </div>
</template>

<style scoped>
</style>
