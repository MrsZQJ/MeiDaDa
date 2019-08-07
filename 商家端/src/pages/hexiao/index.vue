<template>
  <div id="body">
    <div class="top" :style="{'top':topHeight}">
      <i-icon @click="GoBack" type="return" size="24" />
      <!-- <i-input title="<" type="number" placeholder="请输入收货人姓名" /> -->
      <input type="number" placeholder="请输入核销码" />
      <span>核销</span>
    </div>
    <div class="border1px" :style="{'margin-top':margintopHeight}"></div>
    <div class="box" @click="GoToWriteoff">
      <p>美美哒体验店</p>
      <div>
        <span>购物节</span>
        <span>15989468862</span>
        <span>2019.01.09</span>
      </div>
    </div>
    <div class="border1px"></div>
    <div class="box" @click="GoToWriteoff">
      <p>美美哒体验店</p>
      <div>
        <span>购物节</span>
        <span>15989468862</span>
        <span>2019.01.09</span>
      </div>
    </div>
    <div class="border1px"></div>
    <div class="box" @click="GoToWriteoff">
      <p>美美哒体验店</p>
      <div>
        <span>购物节</span>
        <span>15989468862</span>
        <span>2019.01.09</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      //   globalData: ""
    };
  },
  created() {
    // this.topHeight();
  },
  computed: {
    topHeight() {
      var aaa = "";
      wx.getSystemInfo({
        success: res => {
          aaa = res.statusBarHeight + 8 + "px";
        }
      });
      return aaa;
    },
    margintopHeight() {
      var bbb = "";
      wx.getSystemInfo({
        success: res => {
          bbb = res.statusBarHeight + 8+ 31  + "px";
        }
      });
      return bbb;
    }
  },
  methods: {
    GoBack() {
      wx.navigateBack({
        delta: 1
      });
    },
    GoToWriteoff() {
      wx.navigateTo({
        url: "/pages/Write-off/main"
      });
    }
  }
};
</script>

<style scoped>
 
  
   
.top {
  position: fixed;
  /* top: 60px; */
}
.top i-icon {
  float: left;
  line-height: 25px;
}
.top input {
  float: left;
  font-size: 13px;
  width: 234px;
  height: 31px;
  margin-left: 10px;
}
.top span {
  color: #333333;
  font-size: 13px;
  /* line-height: 25px; */
  position: absolute;
  left: 230px;
  top: 8px;
}
.box {
  width: 375px;
  height: 80px;
  color: #999999;
  font-size: 15px;
}
.box p {
  margin-top: 14px;
  margin-left: 15px;
}
.box div {
  padding: 0 15px 0px 15px;
  display: flex;
  justify-content: space-between;
}
.box div span {
  line-height: 41px;
}
</style>
