<template>
  <div id="app">
    <AppHeader />
    <AlbumSection />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AlbumSection from "./components/AlbumSection.vue";

export default {
  name: "App",
  data() {
    return {};
  },
  components: {
    AppHeader,
    AlbumSection,
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: sans-serif;
}

body {
  background-color: #1e2d3b;
  height: 100vh;
}
</style>
