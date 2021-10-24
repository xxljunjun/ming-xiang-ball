
### 一、安装项目
+ npm install -g @vue/cli
+ vue create -p dcloudio/uni-preset-vue 你的项目名

### 二、安装sass
+ cnpm install node-sass@4.12.0 -D
+ cnpm install sass-loader@8.0.2 -D
***需要注意版本问题***
+ 在package.json中的版本要写死！！！

#### 三、如何调试uniapp的微信小程序
+ 1、安装微信者开发工具
+ 2、在h-builder上设置微信者开发工具的安装路径
+ 3、在h-builder上设置端口号http://10.240.5.230:64579
+ 4、在h-builder上运行到小程序
+ 5、发行

#### 四、pages.json配置tabBar
```
{
			"path": "pages/home/index",
			"style": {
				"navigationBarTitleText": "",
				"navigationStyle": "custom", //取消默认导航栏
				"animationType": "none" //页面跳转动画
			}
		},

```
#### 五、配置了appid才能用微信开发者工具的代码上传和预览功能。

### 六、状态栏的处理
```
<style>
	/*每个页面公共css */
	.status_bar {
    height: var(--status-bar-height);
    width: 100%;
    margin-top: 40rpx;
  }
</style>

<view class="status_bar">
      <!-- 这里是状态栏 -->
</view>
```
