<template>
  <div id="app">
    <CardFilm
      v-for="(film, index) in films"
      :key="index"
      :title="film.title"
      :description="film.description"
    > </CardFilm>
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
