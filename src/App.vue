<template>
  <div id="app">
    <AppHeader :genres-list="genresList" @genre-change="setSelectedGenre" />
    <AlbumSection
      :selected-genre="selectedGenre"
      @fetched-genres="setGenresList"
    />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AlbumSection from "./components/AlbumSection.vue";

export default {
  name: "App",
  data() {
    return {
      selectedGenre: "",
      genresList: ["Rock", "Metal", "Pop"],
    };
  },
  components: {
    AppHeader,
    AlbumSection,
  },
  methods: {
    setSelectedGenre(genre) {
      this.selectedGenre = genre;
    },
    setGenresList(genres) {
      this.genresList = genres;
    },
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
