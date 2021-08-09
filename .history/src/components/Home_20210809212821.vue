<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <div class="row" v-for="gambar in gambar" :key="gambar.id">
      <img class="col-sm" :src="gambar.download_url" width="200" />
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Home',
  props: {
    msg: String,
  },
  data() {
    return {
      url: 'https://picsum.photos/v2/list?page=1&limit=100',
      gambar: [],
    };
  },
  methods: {
    getGambar() {
      axios
        .get(this.url)
        .then((data) => {
          this.gambar = data.data;
        })
        .catch(() => {
          alert('error load data');
        });
    },
  },
  mounted() {
    this.getGambar();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: black;
}
</style>
