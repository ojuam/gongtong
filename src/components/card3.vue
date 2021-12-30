<template>
<div class="container">
  <div class="card-box3">
    <div class="content3">
      <h4>基金报告</h4>
    
      <ul v-for="item in teamlist" :key="item">
        <li><a :href="'/#/fund/'+item.id">{{item.title}}</a></li>
      </ul>
    </div>
  </div>
</div>
</template>

<script>
import Box3 from '../components/box3.vue'
import bus from '../assets/bus.js'

export default {
  name: 'Card3',
  data() {
      return {
        teamlist:[]
        
      };
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
            pagenum:'3',
            pagesize:'8'
          }
          
          
        })
        
        this.teamlist=res.data.data
        bus.$emit('data',res.data.data[0].content)
        bus.$emit('data1',res.data.data[0].title)


      }
  },
  components: {
      Box3,
      bus
    }
    
    
  }
</script>

<style>
  .card-box3 {
    margin: 50px;
    position:relative;
    width: 300px;
    height: 400px;
    /* display: flex; */
    justify-content: center;
    align-items: center;
    background-color:rgba(252, 240, 216,0.9);
    
    
  }
  .content3{
    text-align: center;
  }
</style>