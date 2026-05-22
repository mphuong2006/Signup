<script setup>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap/dist/js/bootstrap.bundle.min.js'
import b1 from './components/b1.vue';
import Header from './layouts/Header.vue';
import Footer from './layouts/Footer.vue';
</script>

<template>
 
   <Header />

  <main class="container mt-3">
    <b1 />
  </main>

  <Footer />
 
</template>

