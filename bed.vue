<template>
  <view class="container">
    <view class="title">床位管理</view>
    <view class="bed-list">
      <view class="bed-item" v-for="bed in beds" :key="bed.bed_id">
        <text class="student-name">{{ bed.student_name }}</text>
        <text class="room-number">{{ bed.room_number }}</text>
        <view class="actions">
          <text class="action" @click="editBed(bed)">编辑</text>
          <text class="action" @click="deleteBed(bed)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-bed-action" @click="addBed">添加新床位</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      beds: [
        // 这里可以填充一些示例数据
        { bed_id: 1, student_id: 1, student_name: '小明', room_number: 101 },
        // ...其他床位数据
      ]
    };
  },
  methods: {
    addBed() {
      // 添加新床位的逻辑
    },
    editBed(bed) {
      // 编辑床位的逻辑
    },
    deleteBed(bed) {
      // 删除床位的逻辑
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

.bed-list {
  width: 100%;
}

.bed-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.student-name,
.room-number {
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

.add-bed-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
