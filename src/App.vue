<script setup>
import Header from './components/Header.vue'
import FullCalendar from './components/FullCalendar.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <header>
    <Header />
  </header>

  <main>
    <FullCalendar />
  </main>
  <footer>
    <Footer />
  </footer>
</template>

<style>
@import './assets/base.css';
</style>
