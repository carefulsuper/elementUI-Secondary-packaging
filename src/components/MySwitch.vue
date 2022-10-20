<template>
    <div id="MySwitch">
        <el-switch v-model="value" active-color="#13ce66" @change="handleChange(value)" inactive-color="#ff4949">
        </el-switch>
    </div>
</template>
  
<script>
export default {
    name: 'MySwitch',
    components: {},
    props: {},
    data() {
        return {
            value:true
        }
    },
    methods: {
        handleChange(){
           
                this.value=false
                this.$confirm('关闭后可能导致问题', '确定关闭吗？', {
                confirmButtonText: '确定',
                cancelButtonText: '取消',
            }).then(() => {
            }).catch(() => {
                this.value=true
                this.disabled
            });
            
        }
    }
}
</script>
<style >
</style>
  