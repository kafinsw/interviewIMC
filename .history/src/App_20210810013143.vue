<template>
  <div class="main">
    <a href="http://localhost:8080/">
      <img alt="Vue logo" src="./assets/logoIMC.jpeg" />
    </a>
    <a href="https://imceria.com/" target="_blank"
      ><Home msg="Indie Marketindo Ceria"
    /></a>
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

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 20px;
}
a {
  text-decoration: none;
}
a:hover {
  text-decoration-line: underline;
  text-decoration-color: #0f2b43;
  color: #0f2b43;
}
.main {
  text-align: center;
}
</style>
