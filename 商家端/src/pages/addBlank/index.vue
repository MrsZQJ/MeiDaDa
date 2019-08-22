<template>
  <div id="body">
    <i-cell title="请填写提现银卡信息" label="为了您的资金安全，银行卡人姓名必须与实名认证姓名一致"></i-cell>
    <div class="border1px"></div>
    <i-input :value="value1" title="持卡人" autofocus placeholder="请输入持卡人姓名" />
    <i-input :value="value2" title="银行卡" placeholder="请输入银行卡号"/>
    <i-cell title="选择省" @click="chooseShen" is-link></i-cell>
    <i-cell title="选择市" @click="chooseShen" is-link></i-cell>
    <i-cell title="选择区/县" @click="chooseShen" is-link></i-cell>

    <van-popup :show="blea" position="bottom" @close="onClose" :overlay="true">
      <van-area :area-list="areaList" @cancel="onClose" @confirm="onGo" :value="value3" />
    </van-popup>
  </div>
</template>
<script>
import areaList from "../../../static/vant/area";
export default {
  data() {
    return {
      value1: "",
      value2:"",
      areaList: areaList,
      blea: false,
      value3:""
    };
  },
  methods: {
    chooseShen() {
      this.blea = true;
    },
    onClose() {
      this.blea = false;
    },
    onGo(e) {
      this.blea = false;
      console.log(e.mp.detail.values);
    }
  }
};
</script>
<style scoped>
</style>
