<template>
    <div id="MySelect">
        <el-select v-model="lv" @change="analysischange" placeholder="请选择" clearable @clear="clearInfo">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" >
            </el-option>
        </el-select>
        <el-popconfirm title="这是一段内容确定删除吗？">
            <el-button slot="reference">删除</el-button>
        </el-popconfirm>
    </div>
</template>
<script>
export default {
    name: 'MySelect',
    components: {},
    props: {

    },
    data() {
        return {
            dialogVisible: false,
            options: [{
                value: '选项1',
                label: '黄金糕'
            }, {
                value: '选项2',
                label: '双皮奶'
            }, {
                value: '选项3',
                label: '蚵仔煎'
            }, {
                value: '选项4',
                label: '龙须面'
            }, {
                value: '选项5',
                label: '北京烤鸭'
            }],
            lv: ''
        }
    },
    watch: {
    // 监听输入框内容
    lv(val, olval) {
      console.log(val, olval, "监听");
      this.olval = olval;
    }, },
    methods:{
    analysischange(val) {
      //点击所选位置跳转位置选择的页面
      this.$confirm("确定后将报表展示在<a href='#'>所选位置</a>","提示", {
        confirmButtonText: "确定",
        cancelButtonText: "取消",
        dangerouslyUseHTMLString: true,
        // type: "warning",
      })
        .then(() => {
        console.log(111111111111111);
          this.$message({
            type: "success",
            //点击查看跳转查看的页面
            dangerouslyUseHTMLString: true,
          message: '发布成功，<a href="#">点击查看</a>'
          })
        // this.$router.push('/src/views/HomeView.vue')
        })
        .catch(() => {
          this.$message({
            type: "info",
            message: "已取消切换",
          });
          //将监听到的旧值赋给点击的值
          this.analysiss = this.olval;
        });
      console.log(val, "对比分析下拉框");
    },
    clearInfo(){
      this.$confirm("切换分析类型后系统将清空当前分析结果, 是否继续?","提示", {
        confirmButtonText: "确定",
        cancelButtonText: "取消",
      })
    },
  },
}
</script>

<style>
.el-message-box__title ::before {
  content: "!";
  text-align: center;
    display: inline-block ;
    color:white;
    border-radius: 4rem;
    width: 20px ;
    height: 20px;
     background: #FAAD14;
     margin-right: 10px;
}
a:-webkit-any-link {
  color: green;
  text-decoration: none;
}
</style>