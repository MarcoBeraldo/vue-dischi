<template>
  <header>
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/75/Spotify_icon.png" alt="Logo">
  </header>
</template>

<script>
export default {
    name: "AppHeader",
}
</script>

<style scoped>
header{
    background-color: #2E3A46;
    height: 100px;
    padding: 20px;
}

header> img{
    height: 60px;
}
</style>