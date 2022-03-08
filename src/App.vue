<template>
  <div id="app">

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
  mounted() {},
};
</script>
