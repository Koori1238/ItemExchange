<template>
  <view class="container">
    <text class="title">Welcome to 京大生版ジモティ - Home</text>

    <!-- home page content -->
    <view class="content">
      <text>This is home content...</text>
    </view>

    <!-- bottom navigation -->
    <view class="bottom-nav">
      <view class="nav-button" @click="goToPublish">
        <image class="icon" src="/static/publish.png"></image>
        <text>publish</text>
      </view>
      <view class="nav-button" @click="goToProfile">
        <image class="icon" src="/static/profile.png"></image>
        <text>profile</text>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  methods: {
    goToPublish() {
      uni.switchTab({
        url: '/pages/detail/publish/publish'
      });
    },
    goToProfile() {
      uni.switchTab({
        url: '/pages/detail/profile/profile'
      });
    }
  }
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  justify-content: space-between;
}

.title {
  font-size: 36rpx;
  text-align: center;
  margin-top: 50rpx;
}

.content {
  flex: 1;
  padding: 30rpx;
}

/* bottom nav design */
.bottom-nav {
  display: flex;
  justify-content: space-around;
  padding: 20rpx 0;
  border-top: 1px solid #ccc;
  background-color: #f9f9f9;
}

.nav-button {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 28rpx;
}

.icon {
  width: 50rpx;
  height: 50rpx;
  margin-bottom: 10rpx;
}
</style>

