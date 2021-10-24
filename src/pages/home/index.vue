<template>
  <view class="home">
	  <view class="tabBar">
		  <img src="/static/logo.png" alt="" class="search_icon">
		  <view class="item" v-for="(item,index) in tabBarList" :key='index' @click="clickItem(item.id)">
			  {{item.name}}
		  </view>
	  </view>
	  <view class="home_box" v-if="tabBarId == 1">
		  33333333333333
	  </view>
	   <view class="home_box" v-if="tabBarId == 2">
		   <TabBarTwo/>
	  </view>
	   <view class="home_box" v-if="tabBarId == 3">
		   <TabBarThreen/>
	  </view>
  </view>
</template>

<script>
import TabBarTwo from '@/pages/home/components/tabBar_two.vue'
import TabBarThreen from '@/pages/home/components/tabBar_threen.vue'
export default {
	components:{
		TabBarTwo,
		TabBarThreen
	},
  data() {
    return {
		tabBarId:1,
		tabBarList:[
			{id:1,name:'推荐'},
			{id:2,name:'冥想'},
			{id:3,name:'声音'},
		]
	};
  },
  onLoad() {},
  methods: {
	  /***
	 	@function: 点击tabBar
	  */
	  clickItem(id){
		  console.log(id)
		  this.tabBarId = id
	  }
  },
};
</script>

<style lang="scss" scoped>
.home {
		
}
.tabBar{
		width: 100%;
		height: 150rpx;
		background: red;
	}	
	.search_icon{
		height: 40rpx;
		width: 40rpx;
	}


</style>
