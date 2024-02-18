<template>
  <div>
    <img src="https://mashleanime.com/teaser/img/episode/episode_headline.png" class="fotocomponente" alt="">
    <ul>
        <h2>Temporada 1</h2>
      <li v-for="episode in episodes" :key="episode.id">
        <span v-if="episode.watched">{{ episode.title }} (Visto) </span>
        <span v-else>{{ episode.title }} (No Visto)</span>
        <input type="checkbox" v-model="episode.watched" v-on:change="updateWatchedStatus(episode)">
      </li>
    </ul>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
        episodes: [
  { id: 1, title: "Mash Burnedead y unos músculos bien trabajados", watched: true },
  { id: 2, title: "Mash Burnedead y el laberinto misterioso", watched: false },
  { id: 3, title: "Mash Burnedead y alguien a quien no hacer enfadar", watched: false },
  { id: 4, title: "Mash Burnedead y el mago bastante fuerte", watched: false },
  { id: 5, title: "Mash Burnedead y el compañero que no consigue novia", watched: false },
  { id: 6, title: "Mash Burnedead y la magia de hierro", watched: false },
  { id: 7, title: "Mash Burnedead y el mago titiritero", watched: false },
  { id: 8, title: "Mash Burnedead y Magia Lupus", watched: false },
  { id: 9, title: "Mash Burnedead y el mago acelerador", watched: false },
  { id: 10, title: "Mash Burnedead y el Visionario Divino", watched: false },
  { id: 11, title: "Mash Burnedead y la ley del más fuerte", watched: false },
  { id: 12, title: "Mash Burnedead y el espejo mágico", watched: false }
]
    };
  },
  methods: {
    updateWatchedStatus(episode) {
      // Handle the logic to update the watched status of the episode
      console.log(`Episode ${episode.id} watched status updated: ${episode.watched}`);
    }
  }
};
</script>

<style scoped>
.fotocomponente {
  width: 200px;
  height: auto;
}
</style>
