<template>
  <view class="container">
    <view class="title">退费管理</view>
    <view class="refund-request-list">
      <view class="refund-request-item" v-for="request in refundRequests" :key="request.refund_id">
        <text class="student-name">{{ request.student_name }}</text>
        <text class="amount">{{ request.amount }}</text>
        <text class="request-date">{{ request.request_date }}</text>
        <text class="reason">{{ request.reason }}</text>
        <text class="status">{{ request.status }}</text>
        <view class="actions">
          <text class="action" @click="approveRefundRequest(request)">审批</text>
        </view>
      </view>
    </view>
    <view class="add-refund-request-action" @click="addRefundRequest">添加新退费申请</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      refundRequests: [
        // 这里可以填充一些示例数据
        { refund_id: 1, student_id: 1, student_name: '小明', amount: 500, request_date: '2023-04-03', reason: '提前退学', status: 'pending' },
        // ...其他退费申请
      ]
    };
  },
  methods: {
    addRefundRequest() {
      // 添加新退费申请的逻辑
    },
    approveRefundRequest(request) {
      // 审批退费申请的逻辑
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

.refund-request-list {
  width: 100%;
}

.refund-request-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.student-name,
.amount,
.request-date,
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

.add-refund-request-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
