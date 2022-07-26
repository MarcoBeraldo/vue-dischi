<template>
  <div id="app">
    <AppHeader/>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue"

export default {
  name: 'App',
  components: {
   AppHeader,
  }
}
</script>

<style lang="scss">
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body{
    background-color: #1E2D3B;
    height: 100vh;
  }
</style>
