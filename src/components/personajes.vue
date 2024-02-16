<template>
  <div class="container">
    <!-- Lista de personajes -->
    <div class="marcopersonajes" v-for="personaje in personajes" :key="personaje.id"
      @click="mostrarInformacion(personaje)">
      <img :src= personaje.marco alt="" class="fotos">
      <p>{{personaje.nombre}}</p>
    </div>

    <!-- Div central con información -->
  </div>
   <br>

    <div >
      <div class="info">
        <p ref="info" v-if="mostrarInfo">
          <picture>
            <img :src="personajeSeleccionado.imagenPrincipal"
              width="300" height="627" alt="">
          </picture>
        </p>
      <div ref="info3" v-if="mostrarInfo3">
        <h3 ref="info2"  v-if="mostrarInfo2">{{ personajeSeleccionado.nombre }}</h3>  
        <p>
          {{ personajeSeleccionado.descripcion }}
        </p>
        <div>
          <p>Birthday: {{ personajeSeleccionado.birthday }}</p>
          <p>Height: {{ personajeSeleccionado.height }}</p>
          <p>Foot Size: {{ personajeSeleccionado.footSize }}</p>
          <p>{{ personajeSeleccionado.weakPoint }}</p>
        </div>
        <p ><img :src="personajeSeleccionado.imagenSecundaria" 
          width="401" height="179" alt=""></p>
      </div>
      </div>
    </div>
  
</template>

<script>
import { gsap } from "gsap";
import personajesData from "@/assets/personajes.json";
export default {
  data() {
    return {
      personajes: [],
      personajeSeleccionado: {},
      mostrarInfo: false,
      mostrarInfo2: false,
      mostrarInfo3: false
    };
  },
  mounted() {
    const elements = document.querySelectorAll('.marcopersonajes');
    elements.forEach(el => {
      el.addEventListener('mouseenter', () => {
        gsap.to(el, { rotation: 20, duration: 0.5 });
      });
      el.addEventListener('mouseleave', () => {
        gsap.to(el, { rotation: 0, duration: 0.5 });
      });
    });
  },
  created() {
    this.personajes = personajesData;
    this.mostrarInformacion(this.personajes[0]); // Mostrar el primer personaje al cargar la página
  },
  methods: {
    mostrarInformacion(personaje) {
      this.personajeSeleccionado = personaje;
      // Mostrar nueva información con animaciones GSAP
      this.mostrarInfo = true;
      this.mostrarInfo2 = true;
      this.mostrarInfo3 = true;
      gsap.fromTo(this.$refs.info, { opacity: 0, x: -50 }, { opacity: 1, x: 0, duration: 1 });
      gsap.fromTo(this.$refs.info2, { opacity: 0, y: -70 }, { opacity: 1, y: 0, duration: 2 });
      gsap.fromTo(this.$refs.info3, { opacity: 0, y: -50 }, { opacity: 1, y: 0, duration: 2.5 });
    },
  }
};

document.addEventListener('DOMContentLoaded', function () {
  // Tu código aquí se ejecutará después de que se cargue el DOM
  console.log('El DOM ha sido cargado completamente.');
  // Puedes iniciar GSAP aquí u ejecutar cualquier otra lógica que dependa del DOM
});
</script>

<style scoped>

.container {
  display: flex;
  flex-wrap:nowrap;
}
.fotos{
  
}
.marcopersonajes {
  cursor: pointer;
  margin: 10px;
  
}
.marcopersonajes::hover {
  transform: rotate(90);
  transition: transform 0.5s;
}

.info {
  
  display: flex; 
  flex-direction: row;
}


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
