<template>
  <view class="container">
    <view class="item" @click="onStudentManagement">学生管理</view>
    <view class="item" @click="onClassManagement">班级管理</view>
    <view class="item" @click="onMealPlanManagement">餐饮计划管理</view>
    <view class="item" @click="onBedManagement">床位管理</view>
    <view class="item" @click="onPickupDropoffManagement">接送管理</view>
    <view class="item" @click="onLeaveRequestManagement">请假管理</view>
    <view class="item" @click="onPaymentManagement">缴费管理</view>
    <view class="item" @click="onRefundManagement">退费管理</view>
  </view>
</template>

<script>
export default {
  methods: {
    onStudentManagement() {
      // 学生管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/students'
	  })
    },
    onClassManagement() {
      // 班级管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/class'
	  })
    },
    onMealPlanManagement() {
      // 餐饮计划管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/meal'
	  })
    },
    onBedManagement() {
      // 床位管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/bed'
	  })
    },
    onPickupDropoffManagement() {
      // 接送管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/pickup'
	  })
    },
    onLeaveRequestManagement() {
      // 请假管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/leave'
	  })
    },
    onPaymentManagement() {
      // 缴费管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/studentspay'
	  })
    },
    onRefundManagement() {
      // 退费管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/refund'
	  })
    }
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  padding: 20rpx;
}

.item {
  margin-bottom: 20rpx;
  background-color: #1296db;
  color: #ffffff;
  padding: 20rpx;
  border-radius: 10rpx;
  text-align: center;
}
</style>
