<template>
  <div id="body">
    <!-- 1.0 轮播图 -->
    <swiper
      :indicator-dots="true"
      :autoplay="true"
      :interval="3000"
      :duration="1000"
      indicator-active-color="#ffffff"
      circular
    >
      <block v-for="item in swipers" :key="item.goods_id">
        <navigator :url="item.navigator_url">
          <swiper-item>
            <image :src="item.image_src" />
          </swiper-item>
        </navigator>
      </block>
    </swiper>
    <!-- 购物街分享 -->
    <div class="shopping">
      <div>
        <p>购物节</p>
        <p>¥100.00</p>
        <span>2人团</span>
      </div>
      <!-- <i-icon type="share" size="24" @click="handleOpen1" /> -->
      <img src="../../../static/images/小程序美达达图标/分享/fx_icon@2x.png" @click="handleOpen1" alt />
    </div>
    <div class="clear"></div>
    <div class="serabble">
      <div class="serabble_play">
        <span>拼团玩法</span>
        <span @click="goToMyself">个人中心</span>
      </div>
      <div class="serabble_list">
        <div>
          <img src="../../../static/images/小程序美达达图标/拼团详情/ktct_icon@2x.png" alt />
          <p>开团/参团</p>
        </div>
        <div>
          <img src="../../../static/images/小程序美达达图标/拼团详情/fk_icon@2x.png" alt />
          <p>付款</p>
        </div>
        <div>
          <img src="../../../static/images/小程序美达达图标/拼团详情/fk_icon@2x.png" alt />
          <p>邀请好友</p>
        </div>
        <div>
          <img src="../../../static/images/小程序美达达图标/拼团详情/kt_icon@2x.png" alt />
          <p>成团</p>
        </div>
      </div>
    </div>
    <div class="clear"></div>
    <i-cell title="正在拼团的小伙伴" value="更多" is-link only-tap-footer url="/pages/groupList/main"></i-cell>
    <div class="border1px"></div>
    <div class="serabblePeople">
      <div class="serabblePeople_Left">
        <img src="../../../static/images/user.png" alt />
        <span>美琪</span>
        <i>2人团</i>
      </div>
      <div class="serabblePeople_Right">已成团</div>
    </div>
    <div class="border1px"></div>
    <div class="serabblePeople">
      <div class="serabblePeople_Left">
        <img src="../../../static/images/user.png" alt />
        <span>美琪</span>
        <i>2人团</i>
      </div>
      <div class="serabblePeople_Right">已成团</div>
    </div>
    <div class="clear"></div>
    <div class="datail">
      <p>服务详情</p>
      <span>
        白醋有美容效果，便宜并且到处都有，一般超市都可买
        到。白醋能够达到软化皮肤角质层的作用，还有杀菌的
        作用。正确利用白醋，会有一定的效果，但因为白醋酸
        性比较强，要避免直接把白醋接触脸，最好的方法，是
        用温水将白醋的浓度降低。降低浓度，以免伤害皮肤角
        质层。
      </span>
    </div>
    <div class="footFix" @click="goToPay">¥100.00(单独买)</div>
    <i-action-sheet
      :visible="visible1"
      :actions="actions1"
      show-cancel
      @cancel="handleCancel1"
      @click="handleClickItem"
    />
    <div class="addXiao" v-show="addXiao">
      <span></span>
      点击 [添加小程序] , 下次访问更便捷 >
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      swipers: [
        {
          image_src: "https://www.zhengzhicheng.cn/pyg/banner1.png",
          open_type: "navigate",
          goods_id: 129,
          navigator_url: "/pages/goods_detail/main?goods_id=129"
        },
        {
          image_src: "https://www.zhengzhicheng.cn/pyg/banner2.png",
          open_type: "navigate",
          goods_id: 395,
          navigator_url: "/pages/goods_detail/main?goods_id=395"
        },
        {
          image_src: "https://www.zhengzhicheng.cn/pyg/banner3.png",
          open_type: "navigate",
          goods_id: 38,
          navigator_url: "/pages/goods_detail/main?goods_id=38"
        }
      ],
      visible1: false,
      actions1: [
        {
          name: "转发给好友",
          openType: "share"
        },
        {
          name: "添加到我的小程序"
        }
      ],
      addXiao: false
    };
  },
  created() {
    this.getSwiper();
  },
  methods: {
    getSwiper() {
      wx.login({
        success(res) {
          if (res.code) {
            
          } else {
            console.log("登录失败！" + res.errMsg);
          }
        }
      });
    },
    qingqiu() {
      this.$axios.get(`goods/goodslist?goods_ids=${45}`).then(res => {
        console.log(res);
      });
    },
    handleOpen1() {
      this.visible1 = true;
    },
    handleCancel1() {
      this.visible1 = false;
    },
    goToMyself() {
      wx.navigateTo({
        url: "/pages/PersonalCenter/main"
      });
    },
    goToPay() {
      wx.navigateTo({
        url: "/pages/pay/main"
      });
    },
    handleClickItem(e) {
      // console.log(e.currentTarget.dataset.index);
      // if(e.currentTarget.dataset.index==1){
      this.visible1 = false;
      this.setAdd();
    },
    setAdd() {
      this.addXiao = true;
      setTimeout(() => {
        this.addXiao = false;
      }, 5000);
    }
  }
};
</script>     
<style scoped>
.addXiao {
  color: #000000;
  background-color: #ffffff;
  font-size: 14px;
  padding: 5px 10px;
  border-radius: 10px;
  position: fixed;
  top: 15px;
  right: 20px;
}
.addXiao span {
  display: block;
  position: absolute;
  width: 15px;
  height: 15px;
  transform: rotate(45deg);
  top: -7px;
  right: 47px;
  background-color: #ffffff;
}
swiper {
  width: 750rpx;
  height: 252rpx;
}
swiper image {
  width: 100%;
  height: 100%;
}
.shopping > div {
  float: left;
  margin-left: 15px;
  padding: 15px 0 10px 0;
}
.shopping > div p:nth-child(1) {
  font-size: 15px;
  color: #333333;
  line-height: 22px;
}
.shopping > div p:nth-child(2) {
  font-size: 20px;
  color: #e80000;
  line-height: 24px;
}
.shopping img {
  float: right;
  margin-top: 25px;
  margin-right: 17px;
  width: 25px;
  height: 25px;
}
.shopping {
  position: relative;
  overflow: hidden;
}
.shopping span {
  width: 35px;
  height: 15px;
  border: 1px solid #c7c7cc;
  font-size: 8px;
  text-align: center;
  line-height: 15px;
  position: absolute;
  color: #c7c7cc;
  top: 17px;
  left: 65px;
}
.serabble {
  width: 690rpx;
  height: 138px;
  padding: 12px 15px 15px 15px;
}
.serabble_play {
  overflow: hidden;
}
.serabble_play span:nth-child(1) {
  font-size: 15px;
  color: #333333ff;

  float: left;
}
.serabble_play span:nth-child(2) {
  font-size: 12px;
  color: #ffffffff;
  line-height: 24px;
  text-align: center;
  width: 69px;
  height: 24px;
  border-radius: 30px;
  background-color: #0086f7ff;
  float: right;
}
.serabble_list {
  padding: 22px 12px 15px 12px;
  display: flex;
  justify-content: space-between;
}
.serabble_list img {
  width: 40px;
  height: 40px;
  display: block;
  margin: 0 auto;
  margin-bottom: 10px;
}
.shopping_play .i-cell-text {
  font-size: 15px;
}
.serabblePeople {
  width: 750rpx;
  height: 60px;
  position: relative;
}
.serabblePeople .serabblePeople_Left {
  float: left;
  margin-left: 15px;
  display: flex;
}
.serabblePeople .serabblePeople_Left img {
  width: 40px;
  height: 40px;
  margin-top: 10px;
  margin-right: 10px;
  display: block;
}
.serabblePeople .serabblePeople_Left span {
  color: #333333;
  font-size: 15px;
  line-height: 60px;
}
.serabblePeople .serabblePeople_Left i {
  /* width: 35px; */
  padding: 0px 4px;
  height: 15px;
  border: 1px solid #ea6584;
  font-size: 8px;
  text-align: center;
  line-height: 15px;
  position: absolute;
  color: #ea6584;
  top: 23px;
  left: 100px;
}
.serabblePeople .serabblePeople_Right {
  font-size: 14px;
  color: #ea6584;
  float: right;
  margin-right: 15px;
  line-height: 60px;
}
.datail {
  padding: 0 24px 60px 15px;
}
.datail p {
  margin-top: 3px;
  line-height: 37px;
  font-size: 15px;
  color: #333333;
}
.datail span {
  font-size: 14px;
  color: #666666;
}
.footFix {
  color: #ffffff;
  width: 750rpx;
  height: 49px;
  background-color: #0086f8;
  text-align: center;
  line-height: 49px;
  font-size: 15px;
  position: fixed;
  bottom: 0;
}
</style>
