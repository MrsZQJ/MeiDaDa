<template>
  <div id="body">
    <div class="search">
      <div class="searchBor" @click="GoTohexiao">
        <i-icon type="search" size="20" />
        <!-- <i-input autofocus placeholder="请输入核销码" /> -->
        <input type="text" placeholder="请输入核销码" />
        <div>核销</div>
      </div>
    </div>
    <div class="gouWuJie">
      <span>购物节</span>
      <span>已成功</span>
    </div>
    <div class="border1px"></div>
    <div class="moneyDetail">
      <div class="moneyDetailLeft" @click="GoTogroupDetail">
        <span>2人团</span>
        <span>¥100.00</span>
      </div>
      <div class="moneyDetailRight">
        <div class="rightTwo">
          <p>¥99.00</p>
          <p>总收入</p>
          <p @click="GoToGroupRecords">拼团记录</p>
        </div>
        <div class="rightOne">
          <p>2</p>
          <p>参团人数</p>
          <p>生成海报</p>
        </div>
      </div>
    </div>
    <div class="clear"></div>
    <div class="gouWuJie">
      <span>购物节</span>
      <!-- <span>已成功</span> -->
    </div>
    <div class="border1px"></div>
    <div class="moneyDetail">
      <div class="moneyDetailLeft" @click="GoTogroupDetail">
        <span>2人团</span>
        <span>¥100.00</span>
      </div>
      <div class="moneyDetailRight">
        <div class="rightTwo">
          <p>¥99.00</p>
          <p>总收入</p>
          <p @click="GoToGroupRecords">拼团记录</p>
        </div>
        <div class="rightOne">
          <p>2</p>
          <p>参团人数</p>
          <p>生成海报</p>
        </div>
      </div>
    </div>
    <img
      @click="NewPingTuan"
      src="../../../static/images/小程序美达达图标/新建拼团/xj_icon@2x.png"
      class="NewJia"
      alt
    />
    <span @click="NewPingTuan" class="NewJian">新建拼团</span>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  methods: {
    NewPingTuan() {
      wx.navigateTo({
        url: "/pages/newPingTuan/main"
      });
    },
    GoToGroupRecords() {
      wx.navigateTo({
        url: "/pages/groupRecords/main"
      });
    },
    GoTohexiao() {
      wx.navigateTo({
        url: "/pages/hexiao/main"
      });
    },
    GoTogroupDetail() {
      wx.navigateTo({
        url: "/pages/groupDetail/main"
      });
    }
  }
};
</script>

<style scoped>
 
   
  
.search {
  width: 750rpx;
  height: 49px;
}
.searchBor {
  margin: 10px auto;
  width: 335px;
  height: 19px;
  padding: 6px 0;
}
.searchBor i-icon {
  margin-left: 15px;
  float: left;
}
.searchBor input {
  font-size: 13px;
  margin-left: 10px;
  color: #bebebe;
  float: left;
}
.searchBor div {
  width: 47px;
  border-left: 1px solid #999999;
  font-size: 13px;
  text-align: center;
  float: right;
  color: #333333;
  line-height: 19px;
}
.gouWuJie {
  width: 750rpx;
  height: 49px;
  line-height: 49px;
  font-size: 15px;
  color: #333333;
}
.gouWuJie span:nth-child(1) {
  float: left;
  margin-left: 15px;
}
.gouWuJie span:nth-child(2) {
  float: right;
  margin-right: 15px;
}
.moneyDetail {
  width: 750rpx;
  height: 120px;
}
.moneyDetailLeft {
  margin-left: 15px;
  float: left;
  line-height: 120px;
}
.moneyDetailLeft span:nth-child(1) {
  color: #333333;
  font-size: 15px;
}
.moneyDetailLeft span:nth-child(2) {
  color: #e80000;
  font-size: 20px;
  margin-left: 13px;
}
.moneyDetailRight {
  float: right;
}
.moneyDetailRight div {
  float: right;
  text-align: center;
}
.moneyDetailRight div p:nth-child(1) {
  color: #e70000;
  font-size: 15px;
  margin-top: 16px;
}
.moneyDetailRight div p:nth-child(2) {
  color: #333333;
  font-size: 15px;
  margin-top: 13px;
}
.moneyDetailRight div p:nth-child(3) {
  width: 69px;
  height: 24px;
  border-radius: 30px;
  background-color: #d1d1d1;
  color: #ffffff;
  font-size: 12px;
  text-align: center;
  line-height: 24px;
  margin-top: 17px;
}
.moneyDetailRight div:nth-child(1) {
  margin-right: 24px;
}
.moneyDetailRight div:nth-child(1) p:nth-child(3) {
  background-color: #0086f7;
}
.moneyDetailRight div:nth-child(2) {
  margin-right: 20px;
}
.NewJia {
  width: 60px;
  height: 60px;
  position: fixed;
  left: 50%;
  transform: translate(-50%);
  bottom: 51px;
}
.NewJian {
  color: #333333;
  font-size: 15px;
  position: fixed;
  left: 50%;
  transform: translate(-50%);
  bottom: 20px;
}
</style>
