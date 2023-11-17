<template>
    <div>
        
        <Vue3EasyDataTable
            :headers="columns"
            :items="rows"
            border-cell
        />


    </div>
</template>
<script>
import Vue3EasyDataTable from "vue3-easy-data-table";
import "vue3-easy-data-table/dist/style.css";

export default {
    name: 'dataGrid',
    components: {
        Vue3EasyDataTable,
    },

    data() {
        return {
            columns: [
                { text: "전형요소", value: "admsnFa"},
                { text: "전형방법", value: "admMe"},
                { text: "대학명", value: "unvrsN"},
                { text: "전형", value: "admTy"},
                { text: "계열", value: "dvsn"},
                { text: "모집단위", value: "dprtm"},
                { text: "23 모집인원", value: "rcrtm23"},
                { text: "23 지원인원", value: "aplc23"},
                { text: "23 경쟁률", value: "cmptt23"},
                { text: "22 모집인원", value: "rcrtm22"},
                { text: "22 지원인원", value: "aplc22"},
                { text: "22 경쟁률", value: "cmptt22"},
                { text: "21 모집인원", value: "rcrtm21"},
                { text: "21 지원인원", value: "aplc21"},
                { text: "21 경쟁률", value: "cmptt21"},
                { text: "20 모집인원", value: "rcrtm20"},
                { text: "20 지원인원", value: "aplc20"},
                { text: "20 경쟁률", value: "cmptt20"},
                { text: "19 모집인원", value: "rcrtm19"},
                { text: "19 지원인원", value: "aplc19"},
                { text: "19 경쟁률", value: "cmptt19"},
            ],
            rows: [],
        };
    },

    created() {

    },

    watch: {

    },

    methods: {
        // https://raw.githubusercontent.com/Pwang-je/placement/master/admRatio.json
    }

}
</script>
<style>
    
</style>