<template>
<el-row class="control-right">
  <el-col span="8"><p>&nbsp;</p></el-col>
  <el-col span="6" >
    <el-card :body-style="{ padding: '0px' }">
      <img :src="imglist[0].src" class="image1">
      <div style="padding: 14px;">
        <el-col>
          <h3 style="margin-top: 0;"><a href="http://101.37.116.37:4600" style="text-decoration:none;color:black;">丁洋个人网站</a></h3>
        </el-col>
      </div>
      <div>
        
      </div>
    </el-card>
  </el-col>
  <el-col span="1" ><p>&nbsp;</p></el-col>
  <el-col span="6" >
    <el-card :body-style="{ padding: '0px' }">
      <img :src="imglist[1].src" class="image1">
      <div style="padding: 14px;">
        <el-col >
          <h3 style="margin-top: 0;"><a href="http://101.37.116.37:4500/#/" style="text-decoration:none;color:black;">华银二期</a></h3>
        </el-col>
      </div>
    </el-card>
  </el-col>
</el-row>
</template>

<style>
  
  .image1 {
    width: 100%;
    
    height: 200px;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }
  
  .clearfix:after {
      clear: both
  }
</style>

<script>
export default {
  name: 'Cardteam',
  data() {
    return {
      imglist: [
        {
          name: "1",
          src:  require("@/assets/bp1.png"),
          title: "这是第一张"
        },
        {
          name: "2",
          src: require("@/assets/bp1.png"),
          title: "这是第二张"
        },
        {
          name: "3",
          src: require("@/assets/bp1.png"),
          title: "这是第三张"
        },
        {
          name: "4",
          src: require("@/assets/bp1.png"),
          title: "这是第四张"
        }
      ]
    };
  },
  created() {
    this.getimglist()
  },
  methods: {
    async getimglist(){
        const img1=await this.$http.get('http://101.37.116.37:5000/api/huayin/get-img-main?name=1-1.png')
        const img2=await this.$http.get('http://101.37.116.37:5000/api/huayin/get-img-main?name=1-1.jpg')

        this.imglist[0].name=img1.data.data[0].name
        this.imglist[0].src=img1.data.data[0].location
        this.imglist[1].name=img2.data.data[0].name
        this.imglist[1].src=img2.data.data[0].location
        


      }
  }
}
</script>