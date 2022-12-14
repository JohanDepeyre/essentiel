<template >
  <div id="app">
    <div class="body">


      <SnowFlocons msg="App" />
      <DeezerCard msg="App" />
      <ListMeteo msg="App" />
      <ListRecipes msg="App" />

    </div>
  </div>
</template>

<script>
import ListRecipes from './components/RecipesList.vue'
import ListMeteo from './components/meteo/MeteoList.vue'
import DeezerCard from './components/deezer/DeezerCard.vue'
import SnowFlocons from './components/SnowFlocons.vue'
export default {
  name: 'App',
  components: {
    ListRecipes,
    ListMeteo,
    DeezerCard,
    SnowFlocons
  }
}
let body = document.querySelector("body");
body.style.backgroundColor = "#0E1219";
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  width: 100%;


}




.body {
  height: 100vh;
  background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
  overflow: hidden;

}
</style>
