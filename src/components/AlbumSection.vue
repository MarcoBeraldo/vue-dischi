<template>
  <div>
    <div v-for="album in albums" :key="album.title">
      <AlbumCard
        ::title="album.title"
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
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.albums = res.data.response;
        });
    },
  },
  mounted() {
    this.getAlbums();
  },
};
</script>

<style>
</style>