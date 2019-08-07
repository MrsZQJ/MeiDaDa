<template>
    <div id="body">
        <img class="card" src="../../../static/images/小程序美达达图标/银行卡/建设银行卡@2x.png" alt="">
        <div class="detail">
            <p>￥8000</p>
            <p>可用余额3000</p>
        </div>
        <span class="fix">申请提现</span>
    </div>
</template>
<style scoped>
.card{
    display: block;
    width: 345px;
    height: 115px;
    margin: 9px auto;
}
.detail p:nth-child(1){
    font-size: 29px;
    color: #333333;
    margin-top: 10px;
    margin-left: 23px;
}
.detail p:nth-child(2){
    margin-left: 25px;
    color: #BEBEBE;
    font-size: 13px;
    margin-top: 4px;
}
.fix{
    display: block;
    width: 329px;
    height: 42px;
    background-color: #2287FF;
    color: #FEFEFE;
    font-size: 15px;
    border-radius: 66px;
    margin: 0 auto;
    margin-top: 96px;
    text-align: center;
    line-height: 42px;
}
</style>
