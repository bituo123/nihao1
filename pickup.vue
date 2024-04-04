<template>
	<view class="container">
		<view class="title">接送管理</view>
		<view class="pickup-dropoff-list">
			<view class="pickup-dropoff-item" v-for="record in pickupDropoffRecords" :key="record.record_id">
				<text class="student-name">{{ record.student_name }}</text>
				<text class="pickup-time">{{ record.pickup_time }}</text>
				<text class="dropoff-time">{{ record.dropoff_time }}</text>
				<text class="pickup-person">{{ record.pickup_person }}</text>
				<text class="dropoff-person">{{ record.dropoff_person }}</text>
				<view class="actions">
					<text class="action" @click="editPickupDropoffRecord(record)">编辑</text>
					<text class="action" @click="deletePickupDropoffRecord(record)">删除</text>
				</view>
			</view>
		</view>
		<view class="add-pickup-dropoff-action" @click="addPickupDropoffRecord">添加新接送记录</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				pickupDropoffRecords: [
					// 这里可以填充一些示例数据
					{
						record_id: 1,
						student_id: 1,
						student_name: '小明',
						pickup_time: '2023-04-01T08:00:00',
						dropoff_time: '2023-04-01T18:00:00',
						pickup_person: '李老师',
						dropoff_person: '王阿姨'
					},
					// ...其他接送记录
				]
			};
		},
		methods: {
			addPickupDropoffRecord() {
				// 添加新接送记录的逻辑
			},
			editPickupDropoffRecord(record) {
				// 编辑接送记录的逻辑
			},
			deletePickupDropoffRecord(record) {
				// 删除接送记录的逻辑
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

	.pickup-dropoff-list {
		width: 100%;
	}

	.pickup-dropoff-item {
		display: flex;
		flex-direction: column;
		margin-bottom: 20rpx;
		background-color: #f9f9f9;
		padding: 20rpx;
		border-radius: 10rpx;
	}

	.student-name,
	.pickup-time,
	.dropoff-time,
	.pickup-person,
	.dropoff-person {
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

	.add-pickup-dropoff-action {
		font-size: 28rpx;
		color: #1296db;
		padding: 20rpx;
		background-color: #f9f9f9;
		border-radius: 10rpx;
	}
</style>