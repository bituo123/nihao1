<template>
	<view class="container">
		<view class="mask" @click="maskclick()" v-if="showmodel">

		</view>
		<view class="title">员工信息管理</view>
		<view class="employee-list">
			<view class="employee-item" v-for="employee in employees" :key="employee.employee_id">
				<text class="name">{{ employee.name }}</text>
				<text class="role">{{ employee.role }}</text>
				<text class="contact-info">{{ employee.contact_info }}</text>
				<text class="salary">{{ employee.salary }}</text>
				<view class="actions">
					<text class="action edit" @click="editEmployee(employee)">编辑</text>
					<text class="action view" @click="viewEmployee(employee)">查看</text>
					<text class="action delete" @click="deleteEmployee(employee)">删除</text>
				</view>
			</view>
		</view>
		<view class="form-container" v-if="showmodel">
			<form @submit="submitEditEmployee">
				<view class="form-item">
					<text>姓名:</text>
					<input type="text" v-model="editingEmployee.name" placeholder="请输入姓名" />
				</view>
				<view class="form-item">
					<text>职位:</text>
					<input type="text" v-model="editingEmployee.role" placeholder="请输入职位" />
				</view>
				<view class="form-item">
					<text>联系方式:</text>
					<input type="text" v-model="editingEmployee.contact_info" placeholder="请输入联系方式" />
				</view>
				<view class="form-item">
					<text>工资:</text>
					<input type="number" v-model="editingEmployee.salary" placeholder="请输入工资" />
				</view>
				<button form-type="submit">确认</button>
			</form>
		</view>
		<view class="add-employee-action" @click="addEmployee">添加新员工</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				employees: [{
						employee_id: 1,
						name: '张三',
						role: '开发工程师',
						contact_info: '123456789',
						salary: 3000
					},
					{
						employee_id: 2,
						name: '李四',
						role: '产品经理',
						contact_info: '987654321',
						salary: 4000
					},
					{
						employee_id: 3,
						name: '王五',
						role: '设计师',
						contact_info: '555555555',
						salary: 5000
					}
				],
				editingEmployee: null, // 用于存储正在编辑的员工对象
				showmodel: false
			};
		},
		methods: {
			maskclick() {
				this.showmodel = false
				this.editingEmployee = null;
			},
			addEmployee() {
				this.employees.push({
					employee_id: this.employees.length + 1,
					name: '',
					role: '',
					contact_info: '',
					salary: 0
				});
			},
			editEmployee(employee) {
				this.showmodel = true
				this.editingEmployee = {
					...employee
				}; // 复制员工对象
			},
			submitEditEmployee(e) {
				e.preventDefault(); // 阻止表单默认提交行为
				// 更新员工信息
				const index = this.employees.indexOf(this.editingEmployee);
				if (index !== -1) {
					this.employees.splice(index, 1, this.editingEmployee);
				}
				this.editingEmployee = null; // 完成编辑后重置编辑状态
				this.showmodel = false
			},
			viewEmployee(employee) {
				// 查看员工的逻辑
				// 这里我们简单地显示一个对话框来展示员工信息
				uni.showToast({
					title: `姓名: ${employee.name}, 职位:${employee.role}, 联系方式: ${employee.contact_info}, 工资:${employee.salary}`,
					icon: 'none'
				});
			},
			deleteEmployee(employee) {
				// 删除员工的逻辑
				// 这里我们使用confirm对话框来确认删除操作
				uni.showModal({
					title: '删除员工',
					content: '确定要删除该员工吗？',
					success: (res) => {
						if (res.confirm) {
							// 删除员工信息
							const index = this.employees.indexOf(employee);
							if (index !== -1) {
								this.employees.splice(index, 1);
							}
						}
					}
				});
			}
		}
	};
</script>

<style>
	.mask {
		position: fixed;
		background-color: rgba(0, 0, 0, 0.5);
		/* 透明黑色背景，alpha 值为 0.5 */
		width: 100vw;
		/* 宽度为 100%，占据父元素的全部宽度 */
		height: 100vh;
		/* 高度为 100px */
	}

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

	.employee-list {
		width: 100%;
	}

	.employee-item {
		display: flex;
		flex-direction: column;
		margin-bottom: 20rpx;
		background-color: #f9f9f9;
		padding: 20rpx;
		border-radius: 10rpx;
	}

	.name,
	.role,
	.contact-info,
	.salary {
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

	.form-container {
		position: absolute;
		/* 设置绝对定位的元素 */
		top: 50%;
		/* 设置元素顶部偏移为容器的 50% */
		left: 50%;
		/* 设置元素左侧偏移为容器的 50% */
		transform: translate(-50%, -50%);
		/* 使用 transform 属性来调整元素的最终位置 */
		background-color: #ffffff;
		padding: 20rpx;
		border-radius: 10rpx;
	}

	.form-item {
		margin-bottom: 10rpx;
	}

	.form-item input {
		width: 100%;
		padding: 10rpx;
		border: 1rpx solid #ddd;
		border-radius: 5rpx;
	}
</style>