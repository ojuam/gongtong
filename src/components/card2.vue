<template>
  <div class="card-box2">
    <div class="content2">
      <h4>更多新闻</h4>
      <ul v-for="item in newslist" :key="item">
        <li><a :href="'/#/active/'+item.id">{{item.title}}</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
import Box2 from '../components/box2.vue'
import bus from '../assets/bus.js'

export default {
  name: 'Carrd2',
  data () {
    return {
      newslist:[]
    }
  },
  created(){
    this.getarticlelist()
  },
  methods: {
    
      handleChange(val) {
        console.log(val);
      },
      async getarticlelist(){
        const res =await this.$http.get('/dingyang/get-articles',{
          params:{
            title:'',
            type:'',
            pagenum:'2',
            pagesize:'8'
          }
          
          
        })
        
        this.newslist=res.data.data
        bus.$emit('data',res.data.data[0].content)
        bus.$emit('data1',res.data.data[0].title)
        console.log(this.newslist)

      }
    },
    components: {
      Box2,
      bus
    }
}
</script>

<style>
  .container{
    display: flow-root;
  }
  .card-box2 {
    margin: 50px;
    position:relative;
    width: 300px;
    height: 400px;
    /* display: flex; */
    justify-content: center;
    align-items: center;
    background-color:rgba(252, 240, 216,0.9);
    float: left;
  }
  .content2{
    text-align: center;
  }
 
</style>