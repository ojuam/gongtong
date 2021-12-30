<template>
<div style="display: flow-root;">
  <div class="card-box">
    <div class="card-title">
      <h4>公告</h4>
    </div>
    <div class="card-content">
      <h3 style="color:grey;">网站版本</h3>
      <p>目前网站还在测试阶段，仍有一些bug</p>
      <h3 style="color:grey;">产品展示</h3>
      <p>根据监管要求，私募基金产品业绩不在官网披露，最新净值查询请致电公司客服部0755-89811158</p>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Intro',
  data () {
    return {
      msg: '深圳市华银精治资产管理公司是中国顶尖的私募资产管理机构，中国基金业协会首批特别会员，前海股权交易中心首批挂牌企业。目前华银精治管理近百只基金，规模30亿元，投资业绩排列全国前茅，获得2016年和2015年全国私募业绩排名冠军。',
    }
  }
}
</script>

<style>
  .card-box {
    margin: 50px;
    position:relative;
    width: 300px;
    height: 400px;
    /* display: flex; */
    justify-content: center;
    /* align-items: center; */
    background: #e2e2e2;

    
  }
  .card-title{
    padding: 0px;
    box-sizing:border-box;
    color:#fff;
    background-color:rgba(255,154,46,0.7);
    width:100%;
    height: 8%;
    text-align:center;
}
  .card-content{
    padding:20px;
    box-sizing:border-box;
    color:rgb(170, 168, 168);
    background-color:rgba(252, 240, 216,0.9);
    width:100%;
    height: 92%;
}
</style>