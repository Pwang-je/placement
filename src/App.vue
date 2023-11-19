<template>

  <!-- <DataGrid /> -->
  <!-- <vueGrid /> -->

  <div>
    <select v-model="selectedUniversity" @change="fetchData">
      <!-- 학교 선택 옵션 -->
    </select>
    
    <select v-model="selectedDepartment" @change="fetchData">
      <!-- 학과 선택 옵션 -->
    </select>

    <sct-info 
      :selectedUniversity="selectedUniversity"
      :selectedDepartment="selectedDepartment"
    />

  </div>

</template>

<script>
// import DataGrid from './components/testBoard/selectSch.vue'
// import vueGrid from './components/testBoard/schInfo.vue'
import sctInfo from './components/testBoard/sctInfo.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    // DataGrid
    // vueGrid
    sctInfo,
  },

  data() {
    return {
      selectedUniversity: '',
      selectedDepartment: '',
    };
  },

  methods: {
    sendSelectedValues() {
      this.$emit('selected-values', {
        university: this.selectedUniversity,
        department: this.selectedDepartment,
      });
    },
  },


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
