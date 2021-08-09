<template>
  <div class="navbar">
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
  margin-top: 0px;
}
.navbar {
  overflow: hidden;
  background-color: #333;
  position: fixed;
  top: 0;
  width: 100%;
}
</style>
