<script>
export default {
  name: 'Footer',
  methods: {
    scrollToTop() {
      window.scrollTo(0, 0)
    },
  },
}
</script>

<template>
  <footer class="footer">
    <div class="center-content">
      <p>© 2022 - Lernumerique</p>
      <a @click="scrollToTop()">Revenir en haut</a>
    </div>
  </footer>
</template>

<style>
.center-content {
  text-align: center;
  padding: 20px 0;
}
</style>
