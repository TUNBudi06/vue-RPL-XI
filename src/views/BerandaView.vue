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
  <div class="center_block">
    <h1>{{ tulisan }}</h1>
    <h2 v-if="nama">Nama programmer: {{ nama }} <button @click="changeName">change</button></h2>
    <div v-else>
      <input type="text" v-model="inputName" placeholder="Enter your name">
      <button @click="submitName">Submit</button>
    </div>
    <div class="gapclass">
      <label for="angka1">Masukkan angka1: </label>
      <input type="text" name="angka1" id="angka1" v-model="angka1"><br>
    </div>

    <div>
      <label for="angka2">Masukkan angka2: </label>
      <input type="text" name="angka2" id="angka2" v-model="angka2"><br>
    </div>

    <div>
      <button type="button" @click="jumlahkan">Jumlahkan</button>
      <button type="button" @click="perkalian">perkalian</button>
      <button type="button" @click="pembagian">pembagian</button>
      <button type="button" @click="habisDibagi">habisDibagi</button>
      <button type="button" @click="pengurangan">pengurangan</button>
    </div>

    <div>
      <label for="angka2">Hasil perjumlahan: </label> <p>{{ hasilPerjumlahan }}</p>
    </div>
  </div>
</template>

<style scoped>
.center_block {
  justify-content: center;
  align-items: center;
}

.gapclass {
  gap: 1rem;
}

#angka1 {
  padding-left: initial;
}
</style>
