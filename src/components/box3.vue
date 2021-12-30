<template>
  <el-card class="box-card3" style="width:50%;margin-left: 30%;">
      
      <h1>{{title}}</h1>
      <h4 v-html="msg"></h4>
  </el-card>
</template>

<script>
import Card3 from '../components/card3.vue'
import bus from '../assets/bus.js'

export default {
  name: 'Box3',
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
      bus,Card3
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
  .box-card3 {
    margin-top: -500px;
    /* margin: 0 auto; */
    
    height: 800px;
    position:relative;
  }
</style>