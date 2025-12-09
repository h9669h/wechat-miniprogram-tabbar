<script>
import CustomTabBar from '@/components/uni-custom-tabbar/uni-custom-tabbar/CustomTabBar.vue';
export default {
  components: {
    CustomTabBar
  }
};
</script>

<template>
  <view>
    <!-- 传对应页面在list数组中位置的索引值 -->
    <custom-tab-bar :currentIndex="4" />
  </view>
</template>
