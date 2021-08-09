<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Home msg="Indie Market Ceria" />
</template>

<script>
import Home from './components/Home.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Home,
  },
  data() {
    return {
      url: 'https://picsum.photos/v2/list?page=1&limit=100',
      gambar: [],
    };
  },
  methods: {
    getGambar() {
      axios.get(this.url).then((data) => {
        this.gambar = data.data;
      });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
