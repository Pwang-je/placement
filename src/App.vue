<template>

  <!-- <DataGrid /> -->
  <vueGrid />


</template>

<script>
// import DataGrid from './components/testBoard/selectSch.vue'
import vueGrid from './components/testBoard/schInfo.vue'

export default {
  name: 'App',
  components: {
    // DataGrid
    vueGrid
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
