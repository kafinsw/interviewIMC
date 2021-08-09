<template>
  <!-- <div class="row">
    <h1>{{ msg }}</h1>
    <div v-for="gambar in gambar" :key="gambar.id">
      <img class="col" :src="gambar.download_url" />
    </div>
  </div> -->

  <grid-layout
    :layout.sync="layout"
    :col-num="12"
    :row-height="30"
    :is-draggable="true"
    :is-resizable="true"
    :is-mirrored="false"
    :vertical-compact="true"
    :margin="[10, 10]"
    :use-css-transforms="true"
  >
    <grid-item
      v-for="item in layout"
      :x="item.x"
      :y="item.y"
      :w="item.w"
      :h="item.h"
      :i="item.i"
      :key="item.i"
    >
      {{ item.i }}
    </grid-item>
  </grid-layout>
</template>

<script>
import axios from 'axios';
import VueGridLayout from 'vue-grid-layout';

export default {
  name: 'Home',
  props: {
    msg: String,
  },
  components: {
    GridLayout: VueGridLayout.GridLayout,
    GridItem: VueGridLayout.GridItem,
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
