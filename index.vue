<template>
  <view class="container">
    <view class="item" @click="onEmployeeManagement">员工管理</view>
    <view class="item" @click="onAttendanceManagement">考勤管理</view>
    <view class="item" @click="onSalaryManagement">工资管理</view>
  </view>
</template>

<script>
export default {
  methods: {
    onEmployeeManagement() {
      // 员工管理页面的处理逻辑
	  uni.navigateTo({
	  	url:'/pages/index/stuffadd'
	  })
    },
    onAttendanceManagement() {
      // 考勤管理页面的处理逻辑
	  uni.navigateTo({
	    	url:'/pages/index/active'
	    })
    },
    onSalaryManagement() {
      // 工资管理页面的处理逻辑
	  uni.navigateTo({
	    	url:'/pages/index/payment'
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
