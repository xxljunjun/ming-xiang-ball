<template>
  <view class="home">
    <view class="tabBar">
      <img
        src="/static/logo.png"
        alt=""
        class="search_icon"
        @click="goToSearch"
      />
      <view
        class="item"
        :class="{ activity: item.ischoose }"
        v-for="(item, index) in tabBarList"
        :key="index"
        @click="clickItem(item.id)"
      >
        {{ item.name }}
      </view>
    </view>
    <view class="home_box" v-if="tabBarId == 1">
      <div class="myswiper"><Swiper /></div>

      <view class="title">
        <view class="txt">推荐练习</view>
        <view class="all">全部冥想</view>
      </view>
      <div class="myswiper"><Swiper1 /></div>
      <view class="title">
        <view class="txt">推荐声音</view>
        <view class="all">全部声音</view>
      </view>
    </view>
    <view class="home_box" v-if="tabBarId == 2">
      <TabBarTwo />
    </view>
    <view class="home_box" v-if="tabBarId == 3">
      <TabBarThreen />
    </view>
  </view>
</template>

<script>
import TabBarTwo from "@/pages/home/tabBar_two.vue";
import TabBarThreen from "@/pages/home/tabBar_threen.vue";
import Swiper from "@/pages/home/components/swiper.vue";
import Swiper1 from "@/pages/home/components/swiper_1.vue";
export default {
  components: {
    TabBarTwo,
    TabBarThreen,
    Swiper,
    Swiper1,
  },
  data() {
    return {
      tabBarId: 1,
      tabBarList: [
        { id: 1, name: "推荐", ischoose: true },
        { id: 2, name: "冥想", ischoose: false },
        { id: 3, name: "声音", ischoose: false },
      ],
    };
  },
  onLoad() {},
  methods: {
    /***
	 	@function: 点击tabBar
	  */
    clickItem(id) {
      console.log(id);
      this.tabBarId = id;
      this.tabBarList.forEach((val) => {
        if (val.id == id) {
          val.ischoose = true;
        } else {
          val.ischoose = false;
        }
      });
    },
    /***
	 	@function: 跳转搜索页面
	  */
    goToSearch() {},
  },
};
</script>

<style lang="scss" scoped>
/*
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content:定义了多根轴线的对齐方式

order:数值越小越靠前
flex-grow:定义项目的放大比例
flex-shrink:定义了项目的缩小比例
flex-basis:定义了在分配多余空间之前，项目占据的主轴空间（main size）
flex:是flex-grow, flex-shrink 和 flex-basis的简写
align-self:允许单个项目有与其他项目不一样的对齐方式
*/

.home {
  .home_box {
    .title {
      height: 160rpx;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 40rpx;
      box-sizing: border-box;
      .txt {
        font-size: 50rpx;
        font-weight: 600;
      }
      .all {
        height: 60rpx;
        width: 150rpx;
        border-radius: 30rpx;
        border: 1px solid #b3bfc4;
        font-size: 28rpx;
        display: flex;
        align-items: center;
        justify-content: center;
      }
    }
    .myswiper {
      height: 220rpx;
      width: 670rpx;
    }
  }
  .tabBar {
    width: 100%;
    height: 150rpx;
    margin-top: 120rpx;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    font-size: 28rpx;
    .item {
      margin-right: 60rpx;
      &.activity {
        font-size: 60rpx;
        font-weight: 600;
        border-bottom: 16rpx solid #b6c7ff;
        border-radius: 8rpx;
      }
    }
    .search_icon {
      height: 40rpx;
      width: 40rpx;
      margin-left: 80rpx;
      margin-right: 35rpx;
      position: relative;
      top: 30rpx;
    }
  }
}
</style>
