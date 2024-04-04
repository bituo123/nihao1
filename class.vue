<template>
  <view class="container">
    <view class="title">班级管理</view>
    <view class="class-list">
      <view class="class-item" v-for="classItem in classes" :key="classItem.class_id">
        <text class="class-name">{{ classItem.class_name }}</text>
        <text class="teacher-name">{{ classItem.teacher_name }}</text>
        <view class="actions">
          <text class="action" @click="editClass(classItem)">编辑</text>
          <text class="action" @click="deleteClass(classItem)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-class-action" @click="addClass">添加新班级</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      classes: [
        // 这里可以填充一些示例数据
        { class_id: 1, class_name: '一年级一班', teacher_id: 1, teacher_name: '李老师' },
        // ...其他班级数据
      ]
    };
  },
  methods: {
    addClass() {
      // 添加新班级的逻辑
    },
    editClass(classItem) {
      // 编辑班级的逻辑
    },
    deleteClass(classItem) {
      // 删除班级的逻辑
    }
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20rpx;
  background-color: #ffffff;
}

.title {
  font-size: 32rpx;
  color: #1296db;
  margin-bottom: 20rpx;
}

.class-list {
  width: 100%;
}

.class-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.class-name,
.teacher-name {
  font-size: 28rpx;
  color: #1296db;
  margin-bottom: 10rpx;
}

.actions {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.action {
  font-size: 24rpx;
  color: #1296db;
  padding: 10rpx;
  border: 1rpx solid #1296db;
  border-radius: 5rpx;
  margin-right: 10rpx;
}

.add-class-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
