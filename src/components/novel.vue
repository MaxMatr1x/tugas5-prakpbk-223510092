<template>
    <div class="q-pa-md row items-start q-gutter-md">
      <h2>Novel</h2>
      <q-card class="my-card">
        <div class="image-container">
          <img :src="buku2" alt="Book Image">
        </div>
        <q-card-section>
          <div class="text-h6">Bulan</div>
          <div class="text-subtitle2">by Tere Liye</div>
        </q-card-section>
        <q-card-section class="q-pt-none">
          {{ deskripsi }}
        </q-card-section>
      </q-card>
    </div>
  </template>
  
  <script>
  import buku2 from '../assets/buku2.jpg' 
  
  export default {
    data() {
      return {
        deskripsi: 'Menceritakan petualangan tiga sekawan yaitu Ali, Seli, dan Raib yang dibawa oleh Miss Selena dan Av ke Klan Matahari untuk melakukan diplomasi. Av ingin menemui ketua konsil Klan Matahari untuk mencari Federasi saat melawan Tamus. Konsil Klan Matahari ingin menguasai Klan Matahari. Mereka pergi dengan bantuan dari Buku Kehidupan milik Raib. Akhirnya, dengan kelebihan dan kemampuan masing-masing, mereka memutuskan pergi ke Klan Matahari.',
        buku2
      }
    }
  }
  </script>
  
  <style>
  .my-card {
    margin: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  .image-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .my-card img {
    max-width: 50%;
    height: auto;
  }
  </style>
  