<template>
  <div>
    <MySelect></MySelect>
    <MySwitch></MySwitch>
    <SelectView></SelectView>
    <MyUpload></MyUpload>
    <TreeView></TreeView>
  </div>
</template>

<script>
import MySelect from '../components/MySelect.vue';
import MySwitch from '../components/MySwitch.vue'
import SelectView from '@/components/SelectView.vue';
import MyUpload from '@/components/MyUpload.vue';
import TreeView from '@/components/TreeView.vue';
export default {
  components: { MySelect, MySwitch, SelectView, MyUpload, TreeView },
  data() {
    return {
      value: true
      // dialogVisible: false,

      // value: ''
    }
  },
  methods: {
  }}
</script>
<style >

</style>
