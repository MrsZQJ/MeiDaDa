<template>
  <div id="body">
    <canvas
      class="asd"
      style="width: 290px; height: 400px;"
      canvas-id="myCanvas"
      @bindlongtap="canvasIdErrorCallback"
    ></canvas>
    <span @click="shengc">下载图片</span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isShow: false,
      value6: ""
    };
  },
  mounted() {
    this.hebing();
  },
  methods: {
    hebing() {
      const ctx = wx.createCanvasContext("myCanvas");
      ctx.drawImage("/static/images/bgd/11@2x.png", 0, 0, 290, 400);
      //   ctx.drawImage("/static/images/bgd/erweima.png", 0, 0, 100, 100);
      //   ctx.setFillStyle("#ffffff"); //文字颜色：默认黑色
      //   ctx.setFontSize(30); //设置字体大小，默认10
      //   ctx.fillText("拼团", 75, 50); //绘制文本
      ctx.clearRect(15, 80, 260, 290);
      ctx.drawImage("/static/images/bgd/beau.png", 30, 95, 225, 185);
      ctx.setFillStyle("#000000");
      ctx.setFontSize(14);
      ctx.fillText("这是一个标题模板", 30, 305);
      ctx.setFillStyle("#dc3e1b");
      ctx.setFontSize(20);
      ctx.fillText("￥980.00", 30, 330);
      ctx.setFillStyle("#369599");
      ctx.setFontSize(12);
      ctx.fillText("3人团", 120, 327);
      ctx.setFillStyle("#d6d1d7");
      ctx.setFontSize(10);
      ctx.fillText("长按识别小程序码查看商品", 30, 350);
      ctx.drawImage("/static/images/bgd/erweima.png", 195, 295, 62, 62);
      ctx.draw();
    },
    canvasIdErrorCallback() {
      this.shengc();
    },
    shengc() {
      wx.canvasToTempFilePath(
        {
          canvasId: "myCanvas",
          success(res) {
            wx.authorize({
              scope: "scope.writePhotosAlbum",
              success() {
                wx.saveImageToPhotosAlbum({
                  filePath: res.tempFilePath,
                  success() {
                    wx.showToast({
                      title: "图片保存成功"
                    });
                  }
                });
              }
            });
          }
        },
        this
      );
    }
  }
};
</script>

<style scoped>
.asd {
  margin: 20px auto;
}
</style>
