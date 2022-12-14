<template >
  <div id="app">
    <div class="body">
      <SnowFlocons msg="App" />
      <div class="container">

        <div class="row">
          <div class="col-sm-2">
            <DeezerCard msg="App" />
          </div>
          <div class="col-sm-8">
            <ChemineVideo msg="App" />
          </div>
          <div class="col-sm-2">
            <MeteoCard msg="App" />
          </div>
        </div>

      </div>
      <div class="row">
        <div class="col-sm-12 banierre"></div>

      </div>
    </div>

  </div>
</template>

<script>

import DeezerCard from './components/deezer/DeezerCard.vue'
import SnowFlocons from './components/SnowFlocons.vue'
import MeteoCard from './components/meteo/MeteoList.vue'

import ChemineVideo from './components/cheminee/ChemineVideo.vue'
export default {
  name: 'App',
  components: {
    ChemineVideo,
    DeezerCard,
    SnowFlocons,
    MeteoCard,

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

  overflow-x: hidden;
}

.container {
  max-width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

}


.body {

  background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);

  overflow: hidden;

}

.banierre {
  background-image: url("assets/images/bandeau.PNG");
  height: 200px;
}
</style>
