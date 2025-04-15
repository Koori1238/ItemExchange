<template>
  <view class="login-container">
    <view class="form-item">
      <text class="label">Account：</text>
      <input type="text" v-model="username" placeholder="Please input account" />
    </view>

    <view class="form-item">
      <text class="label">Password：</text>
      <input type="password" v-model="password" placeholder="Please input password" />
    </view>

    <button type="primary" @click="login">login</button>

    <view class="tip" v-if="errorMessage">
      <text class="error">{{ errorMessage }}</text>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      errorMessage: ''
    };
  },
  methods: {
    login() {
      if (!this.username || !this.password) {
        this.errorMessage = 'Please enter your complete username and password‌';
        return;
      }

      // login success/fail
      if (this.username === 'admin' && this.password === '123456') {
        uni.showToast({
          title: 'login success',
          icon: 'success'
        });
        // if success
        uni.switchTab({
          url: '/pages/detail/home/home'
        });
      } else {
        this.errorMessage = 'Account or password error';
      }
    }
  }
}
</script>

<style>
.login-container {
  padding: 50rpx;
}

.form-item {
  margin-bottom: 30rpx;
}

.label {
  font-size: 28rpx;
  margin-bottom: 10rpx;
  display: inline-block;
}

input {
  width: 100%;
  height: 80rpx;
  border: 1px solid #ccc;
  border-radius: 10rpx;
  padding: 0 20rpx;
}

button {
  margin-top: 20rpx;
}

.error {
  color: red;
  font-size: 26rpx;
  margin-top: 20rpx;
}
</style>
