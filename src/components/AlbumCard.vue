<template>
  <div class="album-card">
    <img :src="image" :alt="title" />
    <h3 class="album-title">{{ title }}</h3>
    <p class="author-name">{{ author }}</p>
    <p class="album-year">{{ year }}</p>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    title: String,
    image: String,
    author: String,
    year: Number,
  },
};
</script>

<style>
</style>