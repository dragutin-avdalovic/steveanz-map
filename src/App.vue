<template>
  <div id="app">
    <Sidebar></Sidebar>
    <Map></Map>
  </div>
</template>

<script>
import Map from './components/Map.vue'
import Sidebar from "./components/Sidebar";

export default {
  name: 'app',
  components: {
      Sidebar,
    Map
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0;
  display: flex;
  flex-direction: row;
}
body {
  margin: 0;
}

</style>
