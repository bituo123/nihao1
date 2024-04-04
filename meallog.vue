<template>
  <view class="container">
    <view class="title">餐饮记录管理</view>
    <view class="diet-record-list">
      <view class="diet-record-item" v-for="record in dietRecords" :key="record.diet_record_id">
        <text class="student-name">{{ record.student_name }}</text>
        <text class="date">{{ record.date }}</text>
        <text class="food-name">{{ record.food_name }}</text>
        <text class="quantity">{{ record.quantity }}</text>
        <text class="nutrition-info">{{ record.nutrition_info }}</text>
        <view class="actions">
          <text class="action" @click="editDietRecord(record)">编辑</text>
          <text class="action" @click="deleteDietRecord(record)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-diet-record-action" @click="addDietRecord">添加新餐饮记录</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      dietRecords: [
        // 这里可以填充一些示例数据
        { diet_record_id: 1, student_id: 1, student_name: '小明', date: '2023-04-01', food_name: '米饭', quantity: '200g', nutrition_info: '130卡路里，27克碳水化合物，2克蛋白质，0.5克脂肪', remarks: null },
        // ...其他饮食记录
      ]
    };
  },
  methods: {
    addDietRecord() {
      // 添加新餐饮记录的逻辑
    },
    editDietRecord(record) {
      // 编辑餐饮记录的逻辑
    },
    deleteDietRecord(record) {
      // 删除餐饮记录的逻辑
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

.diet-record-list {
  width: 100%;
}

.diet-record-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.student-name,
.date,
.food-name,
.quantity,
.nutrition-info {
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

.add-diet-record-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
