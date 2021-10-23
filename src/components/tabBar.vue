<template>
  <view class="tabBar">
    <div class="item" v-for="(item, index) in list" :key="index">
      <img src="/static/logo.png" alt="" class="logo" />
      <span class="txt">{{ item.name }}</span>
    </div>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        { id: 1, name: "探索" },
        { id: 2, name: "练习" },
        { id: 3, name: "我的" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.tabBar {
  height: 100rpx;
  width: 100%;
  background: #fff;
  position: fixed;
  bottom: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    .logo {
      height: 30rpx;
      width: 50rpx;
    }
    .txt {
      margin-top: 10rpx;
      font-size: 22rpx;
      color: #becad2;
    }
  }
}
</style>
