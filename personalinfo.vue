<template>
  <view class="container">
    <view class="profile-picture" :style="{ backgroundImage: userAvatarStyle }">
      <!-- 背景图设置为头像 -->
    </view>
    <view class="info">
      <text class="name">张三</text>
      <text class="position">管理员</text>
    </view>
    <view class="actions">
      <text class="action" @click="onSettings">设置</text>
      <text class="action" @click="onLogout">退出登录</text>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      userAvatar: 'path/to/avatar.png' // 头像图片的路径
    };
  },
  computed: {
    userAvatarStyle() {
      return `url(${this.userAvatar})`; // 返回一个字符串，包含背景图的 URL
    }
  },
  methods: {
    onSettings() {
      // 设置页面的处理逻辑
    },
    onLogout() {
      // 退出登录的处理逻辑
    }
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 40rpx;
  background-color: #ffffff;
}

.profile-picture {
  width: 150rpx;
  height: 150rpx;
  margin-bottom: 40rpx;
  background-size: cover;
  background-position: center;
}

.info {
  margin-bottom: 20rpx;
}

.name {
  font-size: 32rpx;
  color: #1296db;
}

.position {
  font-size: 24rpx;
  color: #666;
}

.actions {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
}
</style>
