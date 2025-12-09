<template>
  <view class="custom-tab-bar">
    <view v-for="(item, index) in tabBarList" :class="{ selected: this.currentIndex === index }" :key="index">
      <view class="custom-tab-content" @click="switchTab(item.pagePath)">
        <image
          :src="selected === index ? item.selectedIconPath : item.iconPath"
          style="width: 22px; height: 22px"
        ></image>
        <view
          :class="{ selectedColor: selected === index ? true : false }"
          class="custom-tab-text"
          style="font-size: 10px"
        >
          {{ item.text }}
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  props: {
    currentIndex: Number
  },
  data() {
    return {
      currentIndex: 0,
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
  },
  methods: {
    switchTab(url) {
      uni.switchTab({
        url: '/' + url
      });
    }
  }
};
</script>

<style scoped>
.custom-tab-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 50px;
  background-color: #fff;
  border-width: 1px 0px 0px 0px;
  border-style: solid;
  border-color: #eeeeee;
  z-index: 2;
}

.custom-tab-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.custom-tab-text {
  margin-top: 5px;
  color: #999999;
}
.selectedColor {
  color: #ffb800;
}
</style>
