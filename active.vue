<template>
	<view class="container">
		<view class="title">考勤管理</view>
		<view class="attendance-list">
			<view class="attendance-item" v-for="record in attendanceRecords" :key="record.attendance_record_id">
				<text class="employee-name">{{ record.employee_name }}</text>
				<text class="date">{{ record.date }}</text>
				<text class="check-in-time">{{ record.check_in_time }}</text>
				<text class="check-out-time">{{ record.check_out_time }}</text>
				<text class="late">{{ record.late ? '迟到' : '准时' }}</text>
				<text class="early-departure">{{ record.early_departure ? '早退' : '全勤' }}</text>
				<text class="absent">{{ record.absent ? '缺勤' : '出勤' }}</text>
				<view class="actions">
					<text class="action" @click="editAttendance(record)">编辑</text>
					<text class="action" @click="deleteAttendance(record)">删除</text>
				</view>
			</view>
		</view>
		<view class="add-attendance-action" @click="addAttendance">添加新考勤记录</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				attendanceRecords: [
					// 这里可以填充一些示例数据
					{
						attendance_record_id: 1,
						employee_id: 1,
						employee_name: '张三',
						date: '2023-04-01',
						check_in_time: '09:00',
						check_out_time: '18:00',
						late: false,
						early_departure: false,
						absent: false
					},
					// ...其他考勤记录
				]
			};
		},
		methods: {
			addAttendance() {
				// 添加新考勤记录的逻辑
			},
			editAttendance(record) {
				// 编辑考勤记录的逻辑
			},
			deleteAttendance(record) {
				// 删除考勤记录的逻辑
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

	.attendance-list {
		width: 100%;
	}

	.attendance-item {
		display: flex;
		flex-direction: column;
		margin-bottom: 20rpx;
		background-color: #f9f9f9;
		padding: 20rpx;
		border-radius: 10rpx;
	}

	.employee-name,
	.date,
	.check-in-time,
	.check-out-time,
	.late,
	.early-departure,
	.absent {
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

	.add-attendance-action {
		font-size: 28rpx;
		color: #1296db;
		padding: 20rpx;
		background-color: #f9f9f9;
		border-radius: 10rpx;
	}
</style>