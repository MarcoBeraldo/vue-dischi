<template>
  <header>
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/7/75/Spotify_icon.png"
      alt="Logo"
    />
    <SelectFilter
      placeholder="Seleziona Genere"
      :options="genresList"
      @option-change="emitGenreChange"
    />
  </header>
</template>

<script>
import SelectFilter from "./SelectFilter.vue";
export default {
  name: "AppHeader",
  components: { SelectFilter },
  props: {
    genresList: Array,
  },
  methods: {
    emitGenreChange(genre) {
      this.$emit("genre-change", genre);
    },
  },
};
</script>

<style scoped>
header {
  background-color: #2e3a46;
  height: 100px;
  padding: 20px;
}

header > img {
  height: 60px;
}
</style>