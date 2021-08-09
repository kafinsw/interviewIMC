<template>
  <div class="main">
    <a href="http://localhost:8080/">
      <img alt="Vue logo" src="./assets/logoIMC.jpeg" />
    </a>
    <Home msg="Indie Marketindo Ceria" />
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import Home from './components/Home.vue';

export default {
  name: 'App',
  props: {
    msg: String,
  },
  components: {
    Home,
  },
};
</script>

<style scoped>
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
</style>
