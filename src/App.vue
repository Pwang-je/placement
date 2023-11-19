<template>

  <!-- <DataGrid /> -->
  <!-- <vueGrid /> -->

  <div>
    <label for="universitySelect">학교 선택:</label>
    <select v-model="selectedUniversity" id="universitySelect" @change="sendSelectedValues">
      <option value="">-- 선택하세요 --</option>
      <option v-for="(university, index) in universities" :key="index" :value="university">
        {{ university }}
      </option>
    </select>

    <label for="departmentSelect">학과 선택:</label>
    <select v-model="selectedDepartment" id="departmentSelect" @change="sendSelectedValues">
      <option value="">-- 선택하세요 --</option>
      <option v-for="(department, index) in universityDepartments" :key="index" :value="department">
        {{ department }}
      </option>
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
// import axios from 'axios'

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
      universities: [
        '가천대', '가톨릭대', '건국대(서울)', '경기대', '경희대', '광운대', '국민대', '단국대', '덕성여대',
        '동국대', '동덕여대', '명지대', '서강대', '서울과기대', '서울시립대', '서울여대', '성균관대', '세종대',
        '숙명여대', '숭실대', '아주대', '이화여대', '인하대', '중앙대(서울)', '한국공학대', '한국외대(글로벌)',
        '한국외대(서울)', '한국항공대', '한성대', '한양대(서울)', '한양대에리카', '홍익대'
      ],
      universityDepartments: [],
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
