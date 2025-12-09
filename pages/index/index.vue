<script>
import CustomTabBar from '@/components/uni-custom-tabbar/uni-custom-tabbar/CustomTabBar.vue';
export default {
  components: {
    CustomTabBar
  },
  data() {
    return {
      tabBarList: [
        {
          pagePath: 'pages/sensor/index',
          text: '首页',
          iconPath: '../static/images/sensor_gray.png',
          selectedIconPath: '../static/images/sensor_black.png'
        },
        {
          pagePath: 'pages/control/index',
          text: '控制中心',
          iconPath: '../static/images/control_gray.png',
          selectedIconPath: '../static/images/control_black.png'
        },
        {
          pagePath: 'pages/irrigator/index',
          text: '喷泉',
          iconPath: '../static/images/irrigator_gray.png',
          selectedIconPath: '../static/images/irrigator_black.png'
        },
        {
          pagePath: 'pages/camera/index',
          text: '监控',
          iconPath: '../static/images/camera_gray.png',
          selectedIconPath: '../static/images/camera_black.png'
        },
        {
          pagePath: 'pages/member/index/index',
          text: '我的',
          iconPath: '../static/images/user_gray.png',
          selectedIconPath: '../static/images/user.png'
        }
      ]
    };
  }
};
</script>

<template>
  <view>
    <view class="item1">首页</view>
    <!-- 传对应页面在list数组中位置的索引值 -->
    <custom-tab-bar :currentIndex="1" />
  </view>
</template>
