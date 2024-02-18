<template>
    <img src="https://mashleanime.com/teaser/img/top/story_headline.png" class="fotocomponente" alt="">
    <a href="https://mashleanime.com/" target="_blank">
    <img ref="photo" class="foto" src="../../public/mashle.png" alt=""></a>
        <div class="scroll-content">
           <img src="https://mashleanime.com/teaser/img/top/story_text1_1.png" class="fotohistoria" alt="">
           <img src="https://mashleanime.com/teaser/img/top/story_text2_1.png" class="fotohistoria"  alt="fotohistoria">
           <img src="https://mashleanime.com/teaser/img/top/story_text3_1.png" class="fotohistoria"  alt="fotohistoria">
        </div>
    
</template>
<script>
import { gsap } from "gsap";

export default {
  mounted() {
    // Animación de la foto utilizando GSAP
    this.animatePhoto();
  },
  methods: {
    animatePhoto() {
      gsap.to(this.$refs.photo, {
        x: 25, // Cambia la posición horizontal
        y: 20, // Cambia la posición vertical
         // Cambia la rotación
        duration: 1, // Duración de la animación en segundos
        repeat: -1, // Repetir la animación infinitamente
        yoyo: true // Alternar entre el inicio y el final de la animación
      });
    }
  }
};
</script>
<style>
@keyframes slide {

    0%,
    100% {
        top: 0;
    }

    50% {
        top: 10%;
    }
}
.fotocomponente {
    width: 200px;
    height: auto;
  }


.fotohistoria{
    width: 600px;
    height: auto;

}
.foto{
  position: fixed;
  top:5%;
  left: 85%;
}

</style>