<template>
  <view class="container">
    <view class="title">请假管理</view>
    <view class="leave-request-list">
      <view class="leave-request-item" v-for="request in leaveRequests" :key="request.request_id">
        <text class="student-name">{{ request.student_name }}</text>
        <text class="start-date">{{ request.start_date }}</text>
        <text class="end-date">{{ request.end_date }}</text>
        <text class="reason">{{ request.reason }}</text>
        <text class="status">{{ request.status }}</text>
        <view class="actions">
          <text class="action" @click="approveLeaveRequest(request)">审批</text>
        </view>
      </view>
    </view>
    <view class="add-leave-request-action" @click="addLeaveRequest">添加新请假申请</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      leaveRequests: [
        // 这里可以填充一些示例数据
        { request_id: 1, student_id: 1, student_name: '小明', start_date: '2023-04-01', end_date: '2023-04-05', reason: '生病', status: 'pending' },
        // ...其他请假申请
      ]
    };
  },
  methods: {
    addLeaveRequest() {
      // 添加新请假申请的逻辑
    },
    approveLeaveRequest(request) {
      // 审批请假申请的逻辑
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

.leave-request-list {
  width: 100%;
}

.leave-request-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.student-name,
.start-date,
.end-date,
.reason,
.status {
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

.add-leave-request-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
