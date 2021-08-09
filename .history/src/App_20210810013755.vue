<template>
  <div class="main">
    <a href="http://localhost:8080/">
      <img alt="Vue logo" src="./assets/logoIMC.jpeg" />
    </a>
    <Home msg="Indie Marketindo Ceria" />
  </div>
</template>

<script>
import Home from './components/Home.vue';

export default {
  name: 'App',
  components: {
    Home,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 20px;
}
.main {
  text-align: center;
}
a {
  text-decoration: none;
  color: black;
}
a:hover .h1:hover {
  color: blue;
  transform: scale(1.5);
  transition: transform 0.3s;
}
</style>
