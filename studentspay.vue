<template>
  <view class="container">
    <view class="title">缴费管理</view>
    <view class="payment-record-list">
      <view class="payment-record-item" v-for="record in paymentRecords" :key="record.payment_id">
        <text class="student-name">{{ record.student_name }}</text>
        <text class="amount">{{ record.amount }}</text>
        <text class="payment-date">{{ record.payment_date }}</text>
        <text class="payment-method">{{ record.payment_method }}</text>
        <view class="actions">
          <text class="action" @click="editPaymentRecord(record)">编辑</text>
          <text class="action" @click="deletePaymentRecord(record)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-payment-record-action" @click="addPaymentRecord">添加新缴费记录</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      paymentRecords: [
        // 这里可以填充一些示例数据
        { payment_id: 1, student_id: 1, student_name: '小明', amount: 1000, payment_date: '2023-04-01', payment_method: '现金' },
        // ...其他缴费记录
      ]
    };
  },
  methods: {
    addPaymentRecord() {
      // 添加新缴费记录的逻辑
    },
    editPaymentRecord(record) {
      // 编辑缴费记录的逻辑
    },
    deletePaymentRecord(record) {
      // 删除缴费记录的逻辑
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

.payment-record-list {
  width: 100%;
}

.payment-record-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.student-name,
.amount,
.payment-date,
.payment-method {
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

.add-payment-record-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
