<template>
  <el-card class="box-card1" style="width:50%;margin-left: 30%;">
      
      <h1>{{title}}</h1>
      <h4 v-html="msg"></h4>
  </el-card>
</template>

<script>
import Card1 from '../components/card1.vue'
import bus from '../assets/bus.js'

export default {
  name: 'Box1',
  // props:{
  //   articlelist:Array,
  // },
  data () {
    return {
      msg: '',
      title:''
    }
  },
  components: {
      bus,Card1
    },
    watch:{
      '$route':'getPath'
    },
    methods:{
      async getPath(){
        let id = this.$route.params.id
        const res =await this.$http.get('/huayin/show-edit-article/'+id)
        this.title=res.data.data[0].title
        this.msg=res.data.data[0].content
        console.log(id)
      }
    },
  mounted(){
    bus.$on('data',data=>{this.msg = data;});
    bus.$on('data1',data1=>{this.title = data1;});
  }
}
</script>

<style>
  h4{
      font-size: 16px;
      font-weight: 500;
  }
  .box-card1 {
    margin: 0 auto;
    margin-top: 1%;
    height: 800px;
    position:relative;
  }
</style>