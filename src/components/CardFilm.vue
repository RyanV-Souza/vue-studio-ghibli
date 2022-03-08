<template>
  <div class="card">
    <h1>{{title}}</h1>
    <p>{{description}}</p>
  </div>
</template>
<script>
export default {
  name: "CardFilm",
  props: ["title", "description"],
};
</script>

<style >
.card {
  margin: 1rem;
  background: white;
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.2s linear;
  box-shadow: 2px 4px 25px rgba(0, 0, 0, 0.1);
}
.card:hover {
  box-shadow: 2px 8px 45px rgba(0, 0, 0, 0.15);
  transform: translate3d(0, -2px, 0);
}
h1 {
  text-align: center;
  padding: 1.5rem 2.5rem;
  background: black;
  margin: 0 0 2rem 0;
  font-size: 1.5rem;
  color: white;
}

p {
  padding: 0 2.5rem 2.5rem;
  margin: 0;
}

@media screen and (min-width: 600px) {
  .card {
    flex: 1 1 calc(50% - 2rem);
  }
}

@media screen and (min-width: 900px) {
  .card {
    flex: 1 1 calc(33% - 2rem);
  }
}
</style>