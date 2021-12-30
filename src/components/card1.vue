<template>
  <div class="card-box1">
    <div class="content1">
      <h4>更多产品</h4>
      <ul v-for="item in teamlist" :key="item">
        <li><a :href="'/#/introduction/'+item.id">{{item.title}}</a></li>
      </ul>
    </div>
  </div>
  
</template>

<script>
import Box1 from '../components/box1.vue'
import bus from '../assets/bus.js'

export default {
  name: 'Card1',
  data () {
    return {
      teamlist:[]
    }
  },
  created() {
    this.getarticlelist()
  },
  methods: {
    async getarticlelist(){
        
        const res =await this.$http.get('/huayin/get-articles',{
          params:{
            title:'',
            type:'',
            pagenum:'1',
            pagesize:'8'
          }
          
          
        })
        
        this.teamlist=res.data.data
        bus.$emit('data',res.data.data[0].content)
        bus.$emit('data1',res.data.data[0].title)

      }
  },
  components: {
      Box1,
      bus
    }
}
</script>

<style>
    .card-box1 {
    margin: 50px;
    position:relative;
    width: 200px;
    height: 400px;
    /* display: flex; */
    justify-content: center;
    align-items: center;
    background-color:rgba(252, 240, 216,0.9);
    float: left;
  }
  .content1{
    text-align: center;
  }
  ul li a{
   text-decoration: none;
   color:rgb(48, 47, 47);
 }
  
</style>