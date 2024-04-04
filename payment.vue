<template>
  <view class="container">
    <view class="title">工资管理</view>
    <view class="salary-list">
      <view class="salary-item" v-for="record in salaryRecords" :key="record.salary_record_id">
        <text class="employee-name">{{ record.employee_name }}</text>
        <text class="payment-date">{{ record.payment_date }}</text>
        <text class="payment-method">{{ record.payment_method }}</text>
        <text class="total-salary">{{ record.total_salary }}</text>
        <view class="actions">
          <text class="action" @click="editSalary(record)">编辑</text>
          <text class="action" @click="deleteSalary(record)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-salary-action" @click="addSalary">添加新工资记录</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      salaryRecords: [
        // 这里可以填充一些示例数据
        { salary_record_id: 1, employee_id: 1, employee_name: '张三', payment_date: '2023-04-01', payment_method: '银行转账', total_salary: 3800 },
        // ...其他工资记录
      ]
    };
  },
  methods: {
    addSalary() {
      // 添加新工资记录的逻辑
    },
    editSalary(record) {
      // 编辑工资记录的逻辑
    },
    deleteSalary(record) {
      // 删除工资记录的逻辑
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

.salary-list {
  width: 100%;
}

.salary-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.employee-name,
.payment-date,
.payment-method,
.total-salary {
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

.add-salary-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
