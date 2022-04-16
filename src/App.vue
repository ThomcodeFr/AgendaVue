<script setup>
import Header from './components/Header.vue'
import FullCalendar from './components/FullCalendar.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <header>
    <Header />
  </header>

  <main class="Agenda_Style">
    <FullCalendar />
  </main>
  <footer>
    <Footer />
  </footer>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700;900&display=swap');
@import './assets/base.css';

.Agenda_Style {
  padding: 20px;
}

</style>
