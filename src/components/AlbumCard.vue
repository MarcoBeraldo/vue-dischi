<template>
  <div class="album-card">
    <div>
      <figure>
        <img :src="image" :alt="title" />
      </figure>
      <h3 class="album-title">{{ title }}</h3>
    </div>
    <div class="info">
      <p class="author-name">{{ author }}</p>
      <p class="album-year">{{ year }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    title: String,
    image: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
.album-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: calc(100% / 5 - 40px);
  height: 500px;
  padding: 20px;
  text-align: center;
  background-color: #2e3a46;
  margin: 20px;
  h3 {
    font-size: 2rem;
    color: white;
    margin: 20px 0;
  }

  .info {
    color: gray;
    font-size: 1.2rem;
    display: flex;
    flex-direction: column;
  }
}
figure {
  width: 100%;
  height: 180px;

  img {
    height: 100%;
    width: 100%;
  }
}
</style>