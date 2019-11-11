<template>
  <view class="cover">
    <view class="mydialog">
      <view>{{message.hint}}</view>
      <view class="ticket" v-if="message.ticket">{{message.ticket}}</view>
      <view>{{message.msg}}</view>
      <view>
        <button class="btn_able" @click="$emit('disNone')">立即去查看</button>
      </view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'mydialog',
  props: [
    'message',
    'isDialog'
  ],
}
</script>
<style>
body{
  overflow: hidden;
}
</style>
<style scoped>
.cover {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.6);
  position: fixed;
  left: 0;
  top: 0;
  z-index: 9999;   
}
.mydialog {
  width: 242px;
  margin: 50% auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 14px;
  font-weight: 400;
  color: rgba(0,0,0,0.8);
  line-height: 20px;
  background-color: #fff;
  border-radius:10px;
  padding: 30px 0;
}
.mydialog button {
  width: 169px;
  height: 32px;
  margin-top: 30px;
}
.mydialog .ticket {
  width: 209px;
  height: 37px;
  font-size: 26px;
  font-weight: 500;
  color: #e6081f;
  line-height: 37px;
  text-align: center;
}
.btn_able {
  color: #fff;
  font-size: 14px;
  line-height: 32px;
  background: #f26978;
  border-radius: 4px;
}
</style>
