<template>
  <v-grid 
    :source="filteredRows" 
    :columns="columns" 
    :filter="filterConfig"
    :filter-names="filterNames"
  />
</template>

<script>
import axios from "axios";
import VGrid from "@revolist/vue3-datagrid";

export default {
  name: "App",
  data() {
    return {
      columns: [
        {
          name: "전형요소",
          prop: "admsnFa",
        },
        {
          name: "전형방법",
          prop: "admMe",
        },
        {
          name: "대학명",
          prop: "unvrsN",
          filter: true, // 학교명에 대한 필터 활성화
        },
        {
          name: "전형",
          prop: "admTy",
        },
        {
          name: "계열",
          prop: "dvsn",
        },
        {
          name: "모집단위",
          prop: "dprtm",
        },
        {
          name: "2023 모집인원",
          prop: "2023Rcrtm",
        },
        {
          name: "2023 지원인원",
          prop: "2023Aplc",
        },
        {
          name: "2023 경쟁률",
          prop: "2023Cmptt",
        },
        {
          name: "2022 모집인원",
          prop: "2022Rcrtm",
        },
        {
          name: "2022 지원인원",
          prop: "2022Aplc",
        },
        {
          name: "2022 경쟁률",
          prop: "2022Cmptt",
        },
        {
          name: "2021 모집인원",
          prop: "2021Rcrtm",
        },
        {
          name: "2021 지원인원",
          prop: "2021Aplc",
        },
        {
          name: "2021 경쟁률",
          prop: "2021Cmptt",
        },
        {
          name: "2020 모집인원",
          prop: "2020Rcrtm",
        },
        {
          name: "2020 지원인원",
          prop: "2020Aplc",
        },
        {
          name: "2020 경쟁률",
          prop: "2020Cmptt",
        },
        {
          name: "2019 모집인원",
          prop: "2019Rcrtm",
        },
        {
          name: "2019 지원인원",
          prop: "2019Aplc",
        },
        {
          name: "2019 경쟁률",
          prop: "2019Cmptt",
        },
        // 나머지 컬럼들...
      ],
      rows: [],
      filterConfig: {},
      filterNames: {
        none: '전체', // 선택하지 않음
        empty: '미설정', // 빈 값
        notEmpty: '설정됨', // 값이 있는 경우
        eq: '동일', // Equal
        notEq: '다르게', // Not equal
        begins: '시작함', // Begins with
        contains: '포함함', // Contains
        notContains: '포함하지 않음', // Does not contain
      },
    };
  },

  computed: {
    uniqueSchoolNames() {
      const uniqueNames = new Set(this.rows.map(row => row.unvrsN));
      return Array.from(uniqueNames);
    },
    filteredRows() {
      if (this.filterConfig.unvrsN) {
        return this.rows.filter(row => row.unvrsN === this.filterConfig.unvrsN);
      }
      return this.rows;
    }
  },

  methods: {
    updateFilter(column, value) {
      this.$set(this.filterConfig, column, value);
    },
  },

  watch: {
    rows: {
      handler() {
        this.filterConfig = {};
      },
      deep: true,
    },
  },

  components: {
    VGrid,
  },
  mounted() {
    try {
      axios.get("https://raw.githubusercontent.com/Pwang-je/placement/master/admRatio.json").then((response) => {
        this.rows = response.data;
      });
    } catch (error) {
      console.error("Error fetching data:", error);
    }
  },
};
</script>

<style>
#app {
  height: 900px;
  width: 100%;
}
revo-grid {
  height: 100%;
}
</style>
