<template>
  <header id="header">
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/7/75/Spotify_icon.png"
      alt="Logo"
    />
    <SelectFilter />
  </header>
</template>

<script>
import SelectFilter from "../components/SelectFilter.vue";
export default {
  name: "AppHeader",
  components: {
    SelectFilter,
  },
};
</script>

<style scoped>
#header {
  background-color: #2e3a46;
  height: 100px;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#header > img {
  height: 60px;
}
</style>