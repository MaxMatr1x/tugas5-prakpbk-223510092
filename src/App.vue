<template>
  <q-layout view="hHh lpR fFf">
    <!-- Kode Navbar -->
    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          <q-avatar>
            <img src="./assets/logo.webp">
          </q-avatar>
          MATRIX BOOKSTORE
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs align="left">
        <q-tab name="home" label="Home" icon="home" />
        <q-tab name="pembelian" label="Pembelian" icon="shopping_cart" />
        <q-tab name="tentangKami" label="Tentang Kami" icon="contact_page" />
      </q-tabs>
    </q-header>

    <!-- Drawer Kategori -->
    <q-drawer v-model="leftDrawerOpen" side="left" bordered>
      <q-list>
        <q-item-label header>Kategori</q-item-label>
        <q-item clickable v-ripple @click="showCategories = !showCategories">
          <q-item-section>
            <q-icon name="category" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Kategori</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-show="showCategories" clickable v-ripple @click="currentView = 'komik'">
          <q-item-section avatar>
            <q-icon name="menu_book" />
          </q-item-section>
          <q-item-section>
            Komik
          </q-item-section>
        </q-item>
        <q-item v-show="showCategories" clickable v-ripple @click="currentView = 'novel'">
          <q-item-section avatar>
            <q-icon name="auto_stories" />
          </q-item-section>
          <q-item-section>
            Novel
          </q-item-section>
        </q-item>
        <q-item v-show="showCategories" clickable v-ripple @click="currentView = 'sejarah'">
          <q-item-section avatar>
            <q-icon name="history_edu" />
          </q-item-section>
          <q-item-section>
            Sejarah
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Konten Utama -->
    <q-page-container>
      <div class="q-pa-md">
        <q-carousel
          animated
          v-model="slide"
          navigation
          infinite
          :autoplay="autoplay"
          arrows
          transition-prev="slide-right"
          transition-next="slide-left"
          @mouseenter="autoplay = false"
          @mouseleave="autoplay = true"
        >
          <!-- Menggunakan properti gambar -->
          <q-carousel-slide :name="1" :img-src="banner1" />
          <q-carousel-slide :name="2" :img-src="banner2" />
          <q-carousel-slide :name="3" :img-src="banner3" />
          <q-carousel-slide :name="4" :img-src="banner4" />
        </q-carousel>
      </div>

      <!-- Konten yang dirender secara kondisional -->
      <div v-if="currentView === 'komik'">
        <Komik />
      </div>
      <div v-if="currentView === 'novel'">
        <Novel />
      </div>
      <div v-if="currentView === 'sejarah'">
        <Sejarah />
      </div>
    </q-page-container>

    <!-- Footer -->
    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="./assets/logo.webp">
          </q-avatar>
          <div>NB : Carouselnya agak delay bang...</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

// Mengimpor gambar
import banner1 from './assets/banner1.jpg'
import banner2 from './assets/banner2.jpg'
import banner3 from './assets/banner3.jpg'
import banner4 from './assets/banner4.jpg'

// Mengimpor komponen halaman
import Komik from './components/komik.vue'
import Novel from './components/novel.vue'
import Sejarah from './components/sejarah.vue'

export default {
  components: {
    Komik,
    Novel,
    Sejarah
  },
  setup () {
    const leftDrawerOpen = ref(true)
    const showCategories = ref(true)
    const slide = ref(0)
    const autoplay = ref(true)
    const currentView = ref('home')

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value
    }

    return {
      leftDrawerOpen,
      toggleLeftDrawer,
      showCategories,
      slide,
      autoplay,
      banner1,
      banner2,
      banner3,
      banner4,
      currentView
    }
  }
}
</script>

<style>
.carousel-img {
  max-width: 100%;
  width: 1000px;
  height: inherit;
}
</style>