

<template>
  <div id="app">
    
    <section class="main">
      <personajes />
      <episodios />
    </section>
    
  </div>  
</template>


<script setup>
import personajes from './components/personajes.vue';

import episodios from './components/episodios.vue';
import { gsap } from "gsap";
document.addEventListener('DOMContentLoaded', function() {
    // Tu código aquí se ejecutará después de que se cargue el DOM
    console.log('El DOM ha sido cargado completamente.');
    // Puedes iniciar GSAP aquí u ejecutar cualquier otra lógica que dependa del DOM
});
</script>

<style scoped>

</style>
