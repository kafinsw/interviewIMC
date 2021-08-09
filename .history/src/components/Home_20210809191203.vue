<template>
  <div class="">
    <h1>{{ msg }}</h1>
    <ul v-for="gambar in gambar" :key="gambar.id"></ul>
    <li>{{ gambar.url }}</li>
  </div>
</template>

<script>
export default {
  name: 'Home',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: black;
}
</style>
