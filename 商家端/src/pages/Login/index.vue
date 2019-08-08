<template>
  <div id="body">
    <div :style="{'margin-top':topHeight}" class="login">
      <img src="../../../static/images/图标/图标/logo@2x.png" alt />
      <div class="shu">
        <input type="number" placeholder="手机号码登录" />
        <input type="password" placeholder="请输入密码" />
        <button @click="goToHome">登录</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  created() {},
  computed: {
    topHeight() {
      var aaa = "";
      wx.getSystemInfo({
        success: res => {
          aaa = res.statusBarHeight + "px";
        }
      });
      return aaa;
    }
  },
  methods: {
    goToHome() {
      wx.switchTab({
        url: "/pages/home/main"
      });
    }
  }
};
</script>
<style scoped>
.login {
  text-align: center;
}
.login img {
  width: 73px;
  height: 73px;
  margin-top: 185px;
  margin-bottom: 48px;
}
.login .shu input,
.login .shu button {
  width: 271px;
  height: 45px;
  border-radius: 22px;
  text-align: center;
  border: 1px solid #d3d3d3;
  display: inline-block;
  margin-bottom: 5px;
  color: #a4a4a4;
  font-size: 14px;
}
.login .shu button {
  font-size: 18px;
  background-color: #0086f8;
  line-height: 45px;
  color: #ffffff;
  margin-top: 22px;
}
</style>
