<template>
  <div class="q-pa-md row items-start q-gutter-md">
    <h2>Komik</h2>
    <q-card class="my-card">
      <div class="image-container">
        <img :src="buku1" alt="Book Image">
      </div>
      <q-card-section>
        <div class="text-h6">Doraemon</div>
        <div class="text-subtitle2">by Fujiko F Fujio</div>
      </q-card-section>
      <q-card-section class="q-pt-none">
        {{ deskripsi }}
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import buku1 from '../assets/buku1.jpg' 

export default {
  data() {
    return {
      deskripsi: 'Doraemon (ドラえもん, Doraemon) adalah judul sebuah manga dan anime populer yang dikarang Fujiko F. Fujio (藤子・F・不二雄, nama asli: Hiroshi Fujimoto) sejak Desember 1969 dan berkisah tentang kehidupan seorang anak pemalas kelas 5 sekolah dasar yang bernama Nobita Nobi (野比のび太) yang didatangi oleh sebuah robot kucing bernama Doraemon yang datang dari abad ke-22.',
      buku1
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
