<template>
  <div id="body">
    <!-- <div :style="{'margin-top':topHeight}" class="pos"> -->
    <swiper
      class="swiper"
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
    >
      <block v-for="(item, index) in images" :key="index">
        <swiper-item>
          <div class="swpbox">
            <img :src="item.url" />
            <!-- <img :src="item.url2" /> -->
          </div>
        </swiper-item>
      </block>
    </swiper>
  </div>
  <!-- </div> -->
</template>
<script>
export default {
  data() {
    return {
      indicatorDots: true,
      autoplay: true,
      interval: 3000,
      duration: 500,
      images: [
        {
          url: "/static/images/bgd/11@2x.png",
          url2:"/static/images/bgd/erweima.png"
        },
        {
          url: "/static/images/bgd/22@2x.png",
          url2:"/static/images/bgd/erweima.png"
        },
        {
          url: "/static/images/bgd/33@2x.png",
          url2:"/static/images/bgd/erweima.png"
        },
        {
          url: "/static/images/bgd/44@2x.png",
          url2:"/static/images/bgd/erweima.png"
        }
      ]
    };
  },
  created() {},
  methods: {}
};
</script>
<style scoped>
.swiper {
  height: 100vh;
}
.swpbox{
  height: 100%;
  position: relative;
}
.swpbox img:nth-child(1){
  height: 100%;
  width: 100%;
}
.swpbox img:nth-child(2){
  position: absolute;
  width: 100px;
  height: 100px;
  bottom: 60px;
  left: 50%;
  transform: translate(-50%)
}
</style>