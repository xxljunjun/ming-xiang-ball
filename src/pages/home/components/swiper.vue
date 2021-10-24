<template>
  <view class="swiper-box">
    <swiper
      class="swiper"
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      :circular="true"
      indicator-color="rgba(255, 255, 255, 0.4)"
      indicator-active-color="rgba(255, 255, 255, 1)"
    >
      <swiper-item v-for="(item, index) in 3" :key="index">
        <view class="swiper-item">
          <image src="/static/img_1.jpg" class="swiper-img" />
        </view>
      </swiper-item>
    </swiper>
  </view>
</template>

<script>
export default {
  data() {
    return {
      indicatorDots: true,
      autoplay: true,
      duration: 500,
      interval: 2000,
    };
  },
};
</script>

<style lang="scss" scoped>
.swiper-box {
   width: 100%;
  margin-left: 40rpx;
  .swiper {
     height: 220rpx;
        width: 670rpx;
    .swiper-item {
      height: 220rpx;
        width: 670rpx;
      .swiper-img {
        border-radius: 20rpx;
        height: 220rpx;
        width: 670rpx;
      }
    }
  }
}
</style>