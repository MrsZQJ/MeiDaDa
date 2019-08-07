<template>
  <div id="body">
    <div :style="{'margin-top':topHeight}" class="login">
        <img src="../../../static/images/user.png" alt="">
        <div class="shu">
            <input type="number" placeholder="手机号码登录">
            <input type="password" placeholder="请输入密码">
            <button>登录</button>
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
  }
};
</script>
<style scoped>
.login {
    text-align: center;
}
.login img{
    width: 73px;
    height: 73px;
    margin-top: 185px;
    margin-bottom: 48px;
}
.login .shu input,.login .shu button{
    width: 271px;
    height: 45px;
    border-radius: 22px;
    text-align: center;
    border: 1px solid #D3D3D3;
    display: inline-block;
    margin-bottom: 5px;
    color: #A4A4A4;
    font-size: 14px;
}
.login .shu button{
    font-size: 18px;
    background-color: #0086F8;
    line-height: 45px;
    color: #FFFFFF;
    margin-top: 22px;
}
</style>
