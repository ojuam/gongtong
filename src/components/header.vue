<template>
  <div class="header w">
        <!-- 标志模块 -->
        <div class="logo">
            <img src="../assets/logo1.png">
        </div>
        <!-- 文字导航栏模块 -->
        <div class="nav">
            <ul>
                <li>
                    <router-link to="/introduction/:id?" id="text" ><a href="#">更多内容</a></router-link>
                </li>
                <li>
                    <router-link to="/active/:id?" id="text"><a href="#">关于我们</a></router-link>
                </li>
                <li>
                    <router-link to="/fund/:id?" id="text"><a href="#">投资团队</a></router-link>
                </li>
                <li>
                    <router-link to="/main" id="text"><a href="#">认购流程</a></router-link>
                </li>
                <li>
                    <router-link to="/main" id="text"><a href="#">财富管理</a></router-link>
                </li>
                <li>
                    <router-link to="/main" id="text"><a href="#">财务顾问</a></router-link>
                </li>
            </ul>
        </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1'
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style scoped>
  *{
        margin: 0;
        padding: 0;
    }
    .w{
        width:1200px;
        margin: 0 auto;
    }
    li{
        list-style: none;
    }
    a{
        text-decoration: none;
    }
    .header{
        height: 100px;
        margin:0 auto;
        background-color:#FF9A2E;
        width:100%;
    }
    .logo{
        float: left;
        width: 30%;
        height: 80%;
    }
    .nav{
        float: left;
        margin-left: 60px;
    }
    .nav ul li{
        float: left;
        margin:  10px;
    }
    .nav ul li a{
        display: block;
        height: 100%;
        padding: 0 10px;
        line-height: 60px;
        color: black;
    }
    .nav ul li a:hover{
        color:beige;
    }
    

</style>