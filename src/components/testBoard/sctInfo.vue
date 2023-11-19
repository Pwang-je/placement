<template>
    <div>
        
    </div>
</template>
<script>
export default {
    props: {
        selectedUniversity: String,
        selectedDepartment: String,
    },

    created() {

    },

    methods: {
        createChart() {
            // 여기서 선택한 학교와 학과를 사용해서 차트 생성
            console.log('selected university: ', this.selectedUniversity);
            console.log('selected department: ', this.selectedDepartment);
        }
    }
}
</script>
<style>
    
</style>