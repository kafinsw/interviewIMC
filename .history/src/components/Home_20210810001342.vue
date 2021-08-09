<template>
  <h1>{{ msg }}</h1>
  <div class="row">
    <div
      class="container col-md-4 col-sm-6"
      v-for="gambar in gambar"
      :key="gambar.id"
    >
      <div class="">
        <img class="image" :src="gambar.download_url" />
        <div class="overlay">
          <div class="text">
            <p>{{ gambar.author }}</p>
            <a :href="gambar.url" download
              ><p style="font-size:12px">Download</p></a
            >
          </div>
        </div>
      </div>
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
.row {
  margin-top: 0;
  margin-right: 0;
  margin-left: 0;
}

.container {
  position: relative;
  text-align: center;
  overflow: hidden;
  padding: 0;
  /* padding-right: 0;
  padding-left: 0; */
  margin-right: auto;
  margin-left: auto;
}

.image {
  display: block;
  width: 100%;
  height: auto;
  max-height: 266px;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
}

.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 0;
  transition: 0.5s ease;
  background: rgba(0, 0, 0, 0.5);
}

.container:hover .overlay {
  opacity: 1;
}

.text {
  color: white;
  font-size: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}
</style>
