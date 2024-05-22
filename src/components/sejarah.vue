<template>
    <div class="q-pa-md row items-start q-gutter-md">
      <h2>Sejarah</h2>
      <q-card class="my-card">
        <div class="image-container">
          <img :src="buku3" alt="Book Image">
        </div>
        <q-card-section>
          <div class="text-h6">Sejarah Dunia Yang Disembunyikan</div>
          <div class="text-subtitle2">by Jonathan Black</div>
        </q-card-section>
        <q-card-section class="q-pt-none">
          {{ deskripsi }}
        </q-card-section>
      </q-card>
    </div>
  </template>
  
  <script>
  import buku3 from '../assets/buku3.jpg' 
  
  export default {
    data() {
      return {
        deskripsi: 'Buku Sejarah Dunia yang Disembunyikan merupakan sebuah buku terjemahan karya Jonathan Black yang berjudul “The Secret History of the World”, yang telah terbit pada tahun 2007. Buku ini menjadi salah satu buku sejarah dengan topik yang menarik dan universal, sehingga mampu dibaca oleh siapa saja, tanpa pembacanya harus berpihak pada tokoh manapun. Buku tebal yang terdiri dari 600+ halaman ini akan menyajikan berbagai fakta baru mengenai sejarah dunia yang belum diketahui oleh masyarakat luas, atau mungkin sengaja disembunyikan oleh pihak tertentu.',
        buku3
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
    height: auto
  }
  </style>
  