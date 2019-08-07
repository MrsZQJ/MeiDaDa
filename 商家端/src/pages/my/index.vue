<template>
  <div id="body">
    <div class="touxiang">
      <img src="../../../static/images/小程序美达达图标/头像/头像@2x.png" alt />
      <span>美哒哒</span>
    </div>
    <div class="middle">
      <div class="box">
        <navigator url="/pages/balance/main">
          <p>200</p>
          <span>余额(元)</span>
        </navigator>
      </div>
      <div class="box">
        <navigator url="/pages/tixian/main">
          <p>200</p>
          <span>提现中(元)</span>
        </navigator>
      </div>
      <div class="box">
        <navigator url="/pages/tixianDetail/main">
          <p>200</p>
          <span>提现记录</span>
        </navigator>
      </div>
    </div>
  </div>
</template>
<style scoped>
.touxiang {
  width: 750rpx;
  height: 50px;
  margin-top: 20px;
  margin-bottom: 28px;
}
.touxiang img {
  width: 50px;
  height: 50px;
  margin-left: 20px;
  vertical-align: middle;
}
.touxiang span {
  line-height: 50px;
  margin-left: 10px;
  color: #333333;
  font-size: 15px;
}
.middle .box {
  width: 33%;
  text-align: center;
  display: inline-block;
}
.middle .box p {
  color: #e80000;
  font-size: 20px;
  line-height: 24px;
}
.middle .box span {
  color: #c7c7cc;
  font-size: 14px;
  line-height: 24px;
}
</style>
