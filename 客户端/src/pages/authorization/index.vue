<template>
  <div id="body" v-if="isHide">
    <img src="../../../static/images/user.png" />
    <div class="container">
      <p>申请获取以下权限</p>
      <p>获得你的公开信息(昵称，头像等)</p>
      <button
        class="bottom"
        type="primary"
        lang="zh_CN"
        open-type="getUserInfo"
        @getuserinfo="bindGetUserInfo"
      >授权登录</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isHide: true
    };
  },
  created() {},
  methods: {
    getSett() {
      wx.getSetting({
        success: function(res) {
          if (res.authSetting["scope.userInfo"]) {
            wx.getUserInfo({
              success: function(res) {
                wx.login({
                  success: res => {
                    console.log("用户的code:" + res.code);
                  }
                });
              }
            });
          } else {
            this.isHide = true;
          }
        }
      });
    },
    bindGetUserInfo(e) {
      console.log(e.mp.detail.userInfo);
    }
  }
};
</script>
<style scoped>
#body img {
  width: 120px;
  height: 120px;
  display: block;
  margin: 0 auto;
  margin-top: 100px;
}
.container {
  margin: 0 50px;
  border-top: 2px solid #cccccc;
  padding-top: 15px;
}
.container p {
  font-size: 15px;
  line-height: 30px;
}
.container p:nth-child(2) {
  color: #cccccc;
}
.bottom {
  border-radius: 80rpx;
  margin-top: 32px;
  font-size: 35rpx;
}
</style>