<template>
  <div>
    <h2 style="text-align:center">{{msg}}</h2>
    <p style="text-align:center">{{msg1}}</p>
    <el-divider></el-divider>
  </div>
</template>

<script>
export default {
  name: 'Divider3',
  data () {
    return {
      msg: '关于我们',
      msg1: 'TEAM'
    }
  }
}
</script>

<style>
  h2{
    color: rgb(75, 74, 74);
  }
  p{
    color:darkgrey;
  }
  .el-divider{
    margin:0 auto;
    width: 40%;
  }
</style>