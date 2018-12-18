<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="6"><div class="grid-content bg-purple">1</div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple">2</div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple">3</div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple">4</div></el-col>
    </el-row>
    <div>
      <button type="button" @click="add()">点击</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '测试'
    }
  },
  methods: {
    add () {
      this.$http.post('/api/femaleNameApi',{
        page:1
      }).then((res) => {
        var data = res.data;
        console.log(data.data);
        console.log(1);
        
      }).catch((error) => {
        console.log(error)
      })
    }
  }
}
</script>
<style lang="scss">
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple{
    background: #a04d4d;
    padding: 5px;
    border-radius: 5px;
    color: #fff;
  }
</style>
