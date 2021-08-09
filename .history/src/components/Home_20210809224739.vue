<template>
  <h1>{{ msg }}</h1>
  <div class="container" v-for="gambar in gambar" :key="gambar.id">
    <img class="image" :src="gambar.download_url" />
    <div class="middle">
      <div class="text">John Doe</div>
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
.container {
  position: relative;
  width: 50%;
}

.image {
  opacity: 2;
  display: block;
  width: 100%;
  height: auto;
  transition: 0.5s ease;
  backface-visibility: hidden;
}

.middle {
  transition: 0.5s ease;
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  text-align: center;
}

.container:hover .image {
  opacity: 0.1;
}

.container:hover .middle {
  opacity: 1;
}

.text {
  color: black;
  font-size: 16px;
  padding: 16px 32px;
}
</style>
