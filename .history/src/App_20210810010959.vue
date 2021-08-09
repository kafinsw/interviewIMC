<template>
  <a href="http://localhost:8080/">
    <img alt="Vue logo" src="./assets/logoIMC.jpeg" />
  </a>
  <Home msg="Indie Marketindo Ceria" />
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
</style>
