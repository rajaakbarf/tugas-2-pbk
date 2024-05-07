<template>
  <div>
    <h1 :style="{ color: textColor }">Selamat Datang di Toko Crypto Kami!</h1>
    <p>Silakan masukkan nama Anda untuk mendaftar ke TokoCrypto:</p>
    <input v-model="nama" placeholder="Masukkan Nama" @input="ubahWarnaNama">
    <p :style="{ color: textColor }">Terima kasih, {{ nama }}! Terus pantau kabar terbaru kami.</p>
    <button @click="toggleTema">Ubah Tema Warna</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const nama = ref('');
const textColor = ref('black');
const temaPutih = '#ffffff';
const temaMerah = '#ff0000';

function ubahWarnaNama() {
  if (nama.value.length > 0) {
    textColor.value = 'green'; 
  } else {
    textColor.value = 'black'; 
  }
}

function toggleTema() {
  textColor.value = textColor.value === 'black' ? 'red' : 'black'; 
  document.body.style.backgroundColor = textColor.value === 'red' ? temaMerah : temaPutih; 
}
</script>

<style>

body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 20px;
}
h1 {
  font-size: 24px;
}
p {
  font-size: 16px;
  margin-bottom: 10px;
}
input {
  padding: 8px;
  font-size: 16px;
}
button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}
button:hover {
  background-color: #0056b3;
}
</style>
