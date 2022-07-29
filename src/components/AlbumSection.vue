<template>
  <div class="container">
    <div class="album-section">
      <AlbumCard
        v-for="album in filteredAlbums"
        :key="album.title"
        :title="album.title"
        :image="album.poster"
        :author="album.author"
        :year="album.year"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AlbumCard from "../components/AlbumCard.vue";
export default {
  name: "AlbumSection",
  data() {
    return {
      albums: [],
    };
  },
  components: {
    AlbumCard,
  },
  props: {
    selectedGenre: String,
  },
  computed: {
    filteredAlbums() {
      if (!this.selectedGenre) return this.albums;
      return this.albums.filter((album) => album.genre === this.selectedGenre);
    },
  },
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.albums = res.data.response;
          this.getGenresList();
        });
    },
    getGenresList() {
      const genres = [];

      this.albums.forEach((album) => {
        if (!genres.includes(album.genre)) genres.push(album.genre);
      });
      this.$emit("fetched-genres", genres);
    },
  },
  mounted() {
    this.getAlbums();
  },
};
</script>

<style lang="scss" scoped>
.container {
  max-width: 1400px;
  margin: 0 auto;
}
.album-section {
  margin-top: 40px;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
</style>