<template>
  <div id="body">
    <div class="touxiang">
      <img src="../../../static/images/小程序美达达图标/头像/头像@2x.png" alt />
    </div>
    <div class="border1px"></div>
    <div class="fen">
      <div><span>已支付</span></div>
      <div><span>未支付</span></div>
    </div>
    <div class="border1px"></div>
    <i-cell title="店家名称" v-model="dianjiamingcheng" is-link only-tap-footer url="/pages/groupDetail/main"></i-cell>
    <div class="border1px"></div>
    <i-cell title="活动名称" v-model="huodongmingcheng"></i-cell>
    <div class="border1px"></div>
    <i-cell title="地址" v-model="ip"></i-cell>
    <div class="border1px"></div>
    <i-cell title="电话" v-model="tel"></i-cell>
    <div class="border1px"></div>
    <i-cell title="核销码" v-model="hexiaoma"></i-cell>
    <div class="clear"></div>
    <div class="border1px"></div>
    <i-cell title="店家名称" v-model="dianjiamingcheng" is-link only-tap-footer url="/pages/groupDetail/main"></i-cell>
    <div class="border1px"></div>
    <i-cell title="活动名称" v-model="huodongmingcheng"></i-cell>
    <div class="border1px"></div>
    <i-cell title="地址" v-model="ip"></i-cell>
    <div class="border1px"></div>
    <i-cell title="电话" v-model="tel"></i-cell>
    <div class="border1px"></div>
    <i-cell title="核销码" v-model="hexiaoma"></i-cell>
  </div>
</template>
<script>
export default {
  data(){
    return{
      dianjiamingcheng:"美哒哒美人院",
      huodongmingcheng:"购物节",
      ip:'广州天河区',
      tel:'15989468862',
      hexiaoma:'353234',
    }
  }
}
</script>

<style scoped>
.touxiang {
  width: 750rpx;
  height: 138px;
  text-align: center;
  line-height: 138px;
}
.touxiang img {
  width: 76px;
  height: 76px;
  margin-top: 31px;
}
.fen{
  height: 49px;
  display: flex;
}
.fen>div{
  width: 50%;
  text-align: center;
  line-height: 49px;
}
.fen>div:nth-child(1) span{
  font-size: 15px;
  color: #C7C7CC;
}
.fen>div:nth-child(2) span{
  font-size: 15px;
  color: #3E89E4;
  height: 49px;
  display: inline-block;
  border-bottom: 3px solid #3E89E4;
}
</style>
