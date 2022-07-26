<template>
  <div id="app">
    <AppHeader />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      albums: [],
    };
  },
  components: {
    AppHeader,
  },
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          console.log(res.data);
          this.albums = res.data.response;
        });
    },
  },

  mounted() {
    this.getAlbums();
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-color: #1e2d3b;
  height: 100vh;
}
</style>
