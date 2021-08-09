<template>
  <div class="header">
    <a href="#default" class="logo">CompanyLogo</a>
    <div class="header-right">
      <a class="active" href="#home">Home</a>
      <a href="#contact">Contact</a>
      <a href="#about">About</a>
    </div>
  </div>
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
