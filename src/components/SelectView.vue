<template>
  <div id="SelectView">
    <el-dialog title="提示" icon="el-icon-user-solid
" :visible.sync="dialogVisible" width="30%" :before-close="handleClose">
      <span>这是一段信息</span>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
    <el-select v-model="value" placeholder="请选择" @change="change">
      <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
      </el-option>
    </el-select>
  </div>
</template>
<script>
export default {
  name: "SelectView",
  components: {},
  props: {},
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
      state: ''
    }
  },
  methods: {
    change(state) {
      if (state) {
        this.dialogVisible = true,
        setTimeout(() => {
            this.$message({
              type: "success",
              //点击查看跳转查看的页面
              dangerouslyUseHTMLString: true,
              message: '发布成功，<a href="#">点击查看</a>'
            }).then(()=>{
              this.$message.info('已取消')
            })
        }, 3000);
      }
    },
    handleClose(done) {
      this.$confirm('确认关闭？')
        .then(() => {
          done();
        })
        .catch(() => { });
    }
  }
};
</script>
<style>
.el-message-box__title ::before {
  content: "!";
  text-align: center;
  display: inline-block;
  color: white;
  border-radius: 4rem;
  width: 20px;
  height: 20px;
  background: #FAAD14;
  margin-right: 10px;
}

.el-dialog__title ::before{
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

.el-icon-warning:before {
  color: #FAAD14;

}
</style>