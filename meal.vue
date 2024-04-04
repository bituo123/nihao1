<template>
  <view class="container">
    <view class="title">饮食计划管理</view>
    <view class="meal-plan-list">
      <view class="meal-plan-item" v-for="mealPlan in mealPlans" :key="mealPlan.meal_plan_id">
        <text class="date">{{ mealPlan.date }}</text>
        <text class="menu">{{ mealPlan.menu }}</text>
        <text class="recipe">{{ mealPlan.recipe }}</text>
        <view class="actions">
          <text class="action" @click="editMealPlan(mealPlan)">编辑</text>
          <text class="action" @click="deleteMealPlan(mealPlan)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-meal-plan-action" @click="addMealPlan">添加新饮食计划</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      mealPlans: [
        // 这里可以填充一些示例数据
        { meal_plan_id: 1, date: '2023-04-01', menu: '午餐：米饭、红烧肉、炒青菜；晚餐：面条、鸡蛋汤、凉拌黄瓜', recipe: '午餐：米饭 200g，红烧肉 150g，炒青菜 200g；晚餐：面条 200g，鸡蛋汤 150ml，凉拌黄瓜 100g' },
        // ...其他饮食计划数据
      ]
    };
  },
  methods: {
    addMealPlan() {
      // 添加新饮食计划的逻辑
    },
    editMealPlan(mealPlan) {
      // 编辑饮食计划的逻辑
    },
    deleteMealPlan(mealPlan) {
      // 删除饮食计划的逻辑
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

.meal-plan-list {
  width: 100%;
}

.meal-plan-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.date,
.menu,
.recipe {
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

.add-meal-plan-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
