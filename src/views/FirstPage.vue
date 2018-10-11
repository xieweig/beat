<template>
    <div>page :1
    <el-button type="primary" icon="el-icon-delete" @click="deleteRoute">{{buttonName}}</el-button>
    <el-input v-model="buttonName" label="更改按钮名字"></el-input>
    </div>
</template>

<script>
    export default {
        data:function () {
            return{
                buttonName:'remove page'
            }
        },
        methods:{
            deleteRoute:function () {
                this.$message.success(JSON.stringify(this.$router.options.routes));
                this.$router.options.routes.pop();
            }
        },

    }
</script>

<style scoped>

</style>
