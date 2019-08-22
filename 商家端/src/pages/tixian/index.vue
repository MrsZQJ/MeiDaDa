<template>
  <div id="body">
    <!-- <img class="card" src="../../../static/images/小程序美达达图标/银行卡/建设银行卡@2x.png" alt /> -->
    <div class="card">
      <p>建设银行</p>
      <p>8256 8256 8256 8256</p>
    </div>
    <div class="detail">
      <p>￥8000</p>
      <p>可用余额3000</p>
    </div>
    <i-panel title="圆角输入框">
      <i-input
        :value="value6"
        type="number"
        right
        title="提现金额"
        mode="wrapped"
        placeholder="请输入提现金额"
      />
    </i-panel>
    <span class="fix" @click="showBox">申请提现</span>
    <van-popup :show="isShow" @close="onClose" position="bottom">
      <div class="one">
        <i-icon type="return" size="24" @click="onClose" style="line-height: 49px;" />
        <div>提现方式</div>
      </div>
      <div class="border1px"></div>
      <div class="two">
        <img src="../../../static/images/图标/图标/mima_icon@2x.png" alt />
        <span>中国建设银行(1234)</span>
      </div>
      <div class="border1px"></div>
      <div class="two">
        <img src="../../../static/images/图标/图标/mima_icon@2x.png" alt />
        <span>中国建设银行(1234)</span>
      </div>
      <div class="border1px"></div>
      <div class="two">
        <img src="../../../static/images/图标/图标/mima_icon@2x.png" alt />
        <span>中国建设银行(1234)</span>
      </div>
      <div class="border1px"></div>
      <div class="three">
        <div @click="goToAddBlank">
          <span>添加银行卡提现</span>
        </div>
      </div>
    </van-popup>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isShow: false,
      value6:''
    };
  },
  methods: {
    showBox() {
      this.isShow = true;
    },
    onClose() {
      this.isShow = false;
    },
    goToAddBlank() {
      wx.navigateTo({
        url: "/pages/addBlank/main"
      });
    }
  }
};
</script>

<style scoped>
.card {
  display: block;
  height: 85px;
  margin: 9px auto;
  margin-left: 20px;
  margin-right: 20px;
  padding-left: 30px;
  background-color: #3e6dc7;
  border-radius: 8px;
  color: #ffffff;
  overflow: hidden;
}
.card p:nth-child(1) {
  font-size: 12px;
  line-height: 30px;
  margin-top: 15px;
}
.detail p:nth-child(1) {
  font-size: 29px;
  color: #333333;
  margin-top: 10px;
  margin-left: 23px;
}
.detail p:nth-child(2) {
  margin-left: 25px;
  color: #bebebe;
  font-size: 13px;
  margin-top: 4px;
  margin-bottom: 20px;
}
.fix {
  display: block;
  width: 329px;
  height: 42px;
  background-color: #2287ff;
  color: #fefefe;
  font-size: 15px;
  border-radius: 66px;
  margin: 0 auto;
  margin-top: 78px;
  text-align: center;
  line-height: 42px;
}
.one {
  display: flex;
}
.one div {
  flex: 1;
  text-align: center;
  line-height: 49px;
  font-size: 15px;
}
.two {
  height: 49px;
  line-height: 49px;
}
.two img {
  width: 25px;
  height: 25px;
  margin-left: 15px;
  margin-right: 10px;
  vertical-align: middle;
}
.two span {
  font-size: 15px;
}
.three {
  height: 49px;
}
.three div {
  padding-left: 50px;
  line-height: 49px;
}
.three div span {
  font-size: 15px;
}
</style>
