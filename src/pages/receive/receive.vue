<template>
  <view class="main">
    <view>
      <img class="bg" src="../../static/bg.png" alt="background">
    </view>
    <view class="content">
      <view class="title">输入口令“领奥尔良烤翅”</view>
      <input type="text" v-model="key" placeholder="请输入口令">
      <button @click="getKey" :class="key == null? 'btn_dis' : 'btn_able'" :disabled="key == null? true : false">领取奥尔良烤翅</button>
    </view>
    <view class="space"></view>
    <view>
      <view class="item">
        <span class="inline"></span>
        <view class="pd_10 font_333">活动规则</view>
        <span class="inline"></span></view>
      <view>
        <ul class="list">
          <li>1.直接输入口令“领奥尔良烤翅”即可领取</li>
          <li>2.每个微信ID每天只能领取1次</li>
          <li>3.限量500份，领完结束</li>
          <li>4.奥尔良烤翅券仅限小程序使用，饿了么/美团下单不送</li>
        </ul>
      </view>
    </view>
    <mydialog v-if="isDialog" @disNone="getKey" :message="message"></mydialog>
  </view>
</template>
<script>
import mydialog from '@/pages/template/dialog'
export default {
  data() {
    return {
      key: null,
      message: {
        hint: '恭喜您成功领取',
        ticket: '芝士条券',
        msg: '已放入慕玛披萨小程序中'
      },
      isDialog: false
    }
  },
  components: {
    mydialog
  },
  methods: {
    getKey() {
      this.isDialog = !this.isDialog
      this.key = null
    }
  }
};
</script>
<style scoped>
.bg{
  width: 100vw;
  height: 100vw;
}
.space{
  width: 100%;
  height: 10px;
  background-color: #f8f8f8;
}
.pd_10{
  padding: 10px;
}
.font_333{
  color: #333;
}
.inline{
  width:25px;
  height:2px;
  background-color: rgba(0, 0, 0, 0.1);
}
.content{
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 40px 0;
}
.content .title{
  height: 30px;
  line-height:30px;
  text-align: center;
  font-size: 22px;
  font-weight: 500;
}
.content input{
  margin: 20px 0;
}
.content input,
.content button {
  width: 76%;
  height: 40px;
  border-radius:4px;
}
.content input {
  text-align: center;
  border: 1px solid rgba(0, 0, 0, 0.2)
}
.btn_dis{
  color: #fff!important;
  line-height: 40px;
  background:rgba(242,105,120,0.5)!important;
}
.btn_able{
  color: #fff;
  line-height: 40px;
  background:rgba(242,105,120,1);
}
.item{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.list{
  width: 92%;
  font-size: 14px;
  color: #666;
  margin: 0 16px 16px 16px;
}
</style>