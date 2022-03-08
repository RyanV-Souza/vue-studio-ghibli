<template>
  <div id="app">
    <img
      src="./assets/logo.png"
      alt=""
    >
    <div class="container">
      <CardFilm
        v-for="(film, index) in films"
        :key="index"
        :title="film.title"
        :description="film.description"
      > </CardFilm>
    </div>
  </div>
</template>

<script>
import CardFilm from "./components/CardFilm.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    CardFilm,
  },
  data() {
    return {
      films: [],
    };
  },
  mounted() {
    axios.get("https://ghibliapi.herokuapp.com/films").then((res) => {
      let films = res.data;

      this.films = films.map((film) => {
        return {
          title: film.title,
          description: film.description,
        };
      });
    });
  },
};
</script>

<style >
* {
  box-sizing: border-box;
}

#app {
  max-width: 1200px;
  margin: 0 auto;
}

img {
  display: block;
  margin: 1rem auto;
  max-width: 100%;
}

.container {
  display: flex;
  flex-wrap: wrap;
}
</style>