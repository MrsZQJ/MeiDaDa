<template>
  <div id="body">
    <i-input v-model="namePingTuan" right title="拼团活动名称" placeholder="请填写拼团名称" />
    <div class="border1px"></div>
    <div class="changeTime">
      <span @click="startTime">拼团开始时间</span>
      <span @click="endTime">拼团结束时间</span>
    </div>
    <div class="border1px"></div>
    <div class="chooseNum">
      <p>拼团人数</p>
      <div class="box">
        <div>
          <span>100</span>
          <i>|</i>
          <span>人</span>
        </div>
        <div>
          <span>100</span>
          <i>|</i>
          <span>元</span>
        </div>
        <img src="../../../static/images/小程序美达达图标/新建拼团/xj_icon@2x.png" alt />
      </div>
    </div>
    <div class="clear"></div>
    <div class="pingtuanTop">
      <span>拼团页面顶部图</span>
    </div>
    <div class="border1px"></div>
    <div class="border1px"></div>
    <div class="imgJia">
      <img src="../../../static/images/小程序美达达图标/新建拼团/xj_icon@2x.png" alt />
    </div>
    <div class="clear"></div>
    <div class="fuwuDetail">
      <p>服务详情</p>
      <textarea placeholder="请输入服务详情"></textarea>
      <div class="fuwuImg">
        <img src="../../../static/images/小程序美达达图标/新建拼团/xj_icon@2x.png" alt />
      </div>
    </div>
    <div class="clear"></div>
    <i-input v-model="nameNalue" right title="美容院名称" placeholder="请输入美人院名称" />
    <div class="border1px"></div>
    <i-input v-model="ipNalue" right title="地址位置" placeholder="请输入详细地址" />
    <div class="border1px"></div>
    <i-input v-model="telNalue" right title="客服电话" placeholder="请输入客服电话" />
    <div class="border1px"></div>
    <div class="fuwuDetail">
      <p>参团须知</p>
      <textarea v-model="cantuanxuzhi"></textarea>
      <span class="last">发布活动</span>
    </div>
    <van-popup :show="showStartTime" position="bottom" overlay="false" @close="onStartClose">
      <van-datetime-picker
        type="datetime"
        :min-date="minDate1"
        :max-date="maxDate"
        @cancel="inStartClose"
        @input="onInputStart"
        @confirm="closeTimeChange"
      />
    </van-popup>
    <van-popup :show="showEndTime" position="bottom" overlay="false" @close="onEndClose">
      <van-datetime-picker
        type="datetime"
        :min-date="currentDate1"
        :max-date="maxDate"
        @cancel="inEndClose"
        @input="onInputEnd"
        @confirm="closeTimeChange2"
      />
    </van-popup>
  </div>
</template>
<script>
export default {
  data() {
    return {
      cantuanxuzhi:"",
      namePingTuan: "",
      nameNalue:"",
      ipNalue:"",
      telNalue:"",
      minDate1: new Date().getTime(),
      maxDate: new Date(2019, 10, 1).getTime(),
      currentDate1: new Date().getTime(), //用户选择的起始时间
      showStartTime: false, //是否显示开始时间选择框
      currentDate2: new Date().getTime(), //用户选择的结束时间
      showEndTime: false //是否显示结束时间选择框
    };
  },
  methods: {
    //点击取消关闭开始时间选择框
    inStartClose() {
      this.showStartTime = false;
    },
    //点击取消关闭结束时间选择框
    inEndClose() {
      this.showEndTime = false;
    },
    // 关闭时间选择框
    closeTimeChange() {
      this.showStartTime = false;
    },
    closeTimeChange2(){
      this.showEndTime = false;
    },
    // 更新用户开始时间选择
    onInputStart(event) {
      this.currentDate1 = event.mp.detail;
    },
    //更新用户结束时间选择
    onInputEnd(event) {
      this.currentDate2 = event.mp.detail;
    },
    //点击遮罩层关闭开始时间选择框
    onStartClose() {
      this.showStartTime = false;
    },
    //点击遮罩层关闭结束时间选择框
    onEndClose() {
      this.showEndTime = false;
    },
    // 开启开始时间选择框
    startTime() {
      this.showStartTime = true;
    },
    // 开启结束时间选择框
    endTime() {
      this.showEndTime = true;
    }
  }
};
</script>

<style scoped>
 
  
   
.changeTime {
  width: 375px;
  height: 49px;
  color: #333333;
  font-size: 15px;
}
.changeTime span:nth-child(1) {
  margin-top: 14px;
  margin-left: 15px;
  float: left;
}
.changeTime span:nth-child(2) {
  margin-top: 15px;
  margin-right: 15px;
  float: right;
}
.chooseNum {
  width: 375px;
  height: 93px;
}
.chooseNum p {
  color: #333333;
  font-size: 15px;
  margin-top: 14px;
  margin-left: 15px;
  margin-bottom: 17px;
}
.box div {
  width: 101px;
  height: 26px;
  border-radius: 3px;
  border: 1px solid #333333;
  position: relative;
}
.box img {
  float: left;
  width: 50px;
  height: 50px;
  margin-top: -10px;
  margin-left: 31px;
}
.box div:nth-child(1) {
  margin-left: 15px;
  float: left;
}
.box div:nth-child(2) {
  margin-left: 31px;
  float: left;
}
.box div span {
  display: inline-block;
  width: 49%;
  height: 100%;
  line-height: 26px;
  text-align: center;
  color: #333333;
  font-size: 12px;
}
.box div i {
  position: absolute;
  left: 50%;
  transform: translate(-50%);
  top: 5px;
  font-size: 10px;
}
.pingtuanTop {
  width: 375px;
  height: 49px;
}
.pingtuanTop span {
  margin-left: 15px;
  color: #333333;
  font-size: 15px;
  line-height: 49px;
}
.imgJia {
  width: 375px;
  height: 88px;
}
.imgJia img {
  width: 58px;
  height: 58px;
  margin-left: 15px;
  margin-top: 15px;
}
.fuwuDetail p {
  color: #333333;
  font-size: 15px;
  margin-left: 15px;
  margin-top: 14px;
  margin-bottom: 20px;
}
.fuwuDetail textarea {
  width: 324px;
  height: 87px;
  padding: 6px 10px;
  font-size: 15px;
  border: 1px solid #cccccc;
  margin: 0 auto;
}
.fuwuImg {
  padding: 20px 15px;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
}
.fuwuImg img {
  width: 58px;
  height: 58px;
  margin: 5px;
}
.last{
  display: block;
  width: 329px;
  height: 42px;
  background-color: #2287FF;
  border-radius: 66px;
  margin: 39px auto;
  margin-bottom: 30px;
  color:#FEFEFE;
  text-align: center;
  line-height: 42px;
  
}
</style>
