<template>
  <view class="container">
    <view class="title">学生管理</view>
    <view class="student-list">
      <view class="student-item" v-for="student in students" :key="student.student_id">
        <text class="student-name">{{ student.name }}</text>
        <text class="age">{{ student.age }}</text>
        <text class="guardian-contact">{{ student.guardian_contact }}</text>
        <text class="class-name">{{ student.class_name }}</text>
        <view class="actions">
          <text class="action" @click="editStudent(student)">编辑</text>
          <text class="action" @click="deleteStudent(student)">删除</text>
        </view>
      </view>
    </view>
    <view class="add-student-action" @click="addStudent">添加新学生</view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      students: [
        // 这里可以填充一些示例数据
        { student_id: 1, name: '小明', age: 10, guardian_contact: '1112223333', class_id: 1, class_name: '一年级一班' },
        // ...其他学生数据
      ]
    };
  },
  methods: {
    addStudent() {
      // 添加新学生的逻辑
    },
    editStudent(student) {
      // 编辑学生的逻辑
    },
    deleteStudent(student) {
      // 删除学生的逻辑
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

.student-list {
  width: 100%;
}

.student-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 20rpx;
  background-color: #f9f9f9;
  padding: 20rpx;
  border-radius: 10rpx;
}

.student-name,
.age,
.guardian-contact,
.class-name {
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

.add-student-action {
  font-size: 28rpx;
  color: #1296db;
  padding: 20rpx;
  background-color: #f9f9f9;
  border-radius: 10rpx;
}
</style>
