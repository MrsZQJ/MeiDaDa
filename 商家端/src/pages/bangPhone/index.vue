<template>
  <div id="body">
    <div class="title">请输入绑定的手机号码</div>
    <div class="shu">
      <img src="../../../static/images/手机@2x.png" alt />
      <span>手机号码</span>
    </div>
    <input class="ipt" type="number" placeholder="请输入手机号码" />
    <div class="shu">
      <img src="../../../static/images/验证码@2x.png" alt />
      <span>验证码</span>
    </div>
    <div class="por">
      <input class="ipt" type="number" placeholder="请输入验证码" />
      <button class="btn">获取验证码</button>
    </div>
    <i-button @click="handleClick" type="primary" shape="circle" size="small">下一步</i-button>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  methods: {
    handleClick() {
      wx.navigateTo({
        url: "/pages/resetPassword/main"
      });
    }
  }
};
</script>
<style scoped>
.title {
  height: 49px;
  padding-left: 15px;
  line-height: 49px;
  font-size: 15px;
  color: #333333;
  font-weight: 600;
}
.shu {
  height: 49px;
  line-height: 49px;
}
.shu img {
  margin-left: 15px;
  width: 20px;
  height: 20px;
  margin-right: 10px;
  display: inline-block;
  vertical-align: middle;
}
.shu span {
  font-size: 15px;
  color: #333333;
}
.ipt {
  width: 326px;
  height: 49px;
  margin-left: 49px;
  font-size: 15px;
  color: #999999;
}
.por {
  position: relative;
  margin-bottom: 81px;
}
.btn {
  width: 74px;
  height: 24px;
  border-radius: 12px;
  color: #ffffff;
  text-align: center;
  line-height: 24px;
  font-size: 12px;
  background-color: #0086f7;
  padding: 0px;
  position: absolute;
  top: 12px;
  right: 15px;
}
.por .ipt {
  width: 246px;
  margin-right: 80px;
}
</style>
