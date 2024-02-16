

<template>
  <div id="app">
    <personajes />
  </div>
</template>

<script setup>
import personajes from './components/personajes.vue';

import { gsap } from "gsap";
document.addEventListener('DOMContentLoaded', function() {
    // Tu código aquí se ejecutará después de que se cargue el DOM
    console.log('El DOM ha sido cargado completamente.');
    // Puedes iniciar GSAP aquí u ejecutar cualquier otra lógica que dependa del DOM
});
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
