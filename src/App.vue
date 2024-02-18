

<template>
  <div id="app">
   
    <section class="main">
      <historia />
      <episodios />
      <personajes />
    </section>
    
  </div>  
</template>


<script setup>
import personajes from './components/personajes.vue';
import historia from './components/historia.vue';
import episodios from './components/episodios.vue';
import { gsap } from "gsap";



</script>

<style scoped>
  .foto{
    width: 200px;
    height: auto;
  }
</style>
