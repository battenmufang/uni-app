<template>
  <view class="login-container">
    <u-form :model="form" ref="uForm">
      <u-form-item label="用户名" prop="username">
        <u-input 
          v-model="form.username" 
          placeholder="请输入用户名"
          border
        />
      </u-form-item>
      
      <u-form-item label="密码" prop="password">
        <u-input 
          v-model="form.password" 
          placeholder="请输入密码" 
          type="password"
          border
        />
      </u-form-item>
      
      <u-button 
        type="primary" 
        text="提交" 
        :loading="loading"
        @click="handleSubmit"
      ></u-button>
    </u-form>
  </view>
</template>

<script>
export default {
  data() {
    return {
      form: {
        username: '',
        password: ''
      },
      loading: false
    }
  },
  methods: {
    async handleSubmit() {
      // 检查用户名和密码是否为空
      if (!this.form.username.trim() || !this.form.password.trim()) {
        this.$u.toast('请填写完整信息')
        return
      }
      // 显示加载状态
      this.loading = true
      
      try {
        // 向 MySQL 数据库写入数据
        const result = await this.saveToDatabase()
        
        if (result.success) {
          this.$u.toast('提交成功')
          // 清空表单
          this.form.username = ''
          this.form.password = ''
        } else {
          this.$u.toast('提交失败：' + result.message)
        }
      } catch (error) {
        console.error('提交错误:', error)
        this.$u.toast('提交出错，请重试')
      } finally {
        // 隐藏加载状态
        this.loading = false
      }
    },
    
    async saveToDatabase() {
      // 这里替换为你的实际 API 调用
      // 示例使用 uni.request 调用后端接口
      return new Promise((resolve, reject) => {
        uni.request({
          url: 'http://battenmufang.xyz:3000/api/users/register', // 替换为你的实际 API 地址
          method: 'POST',
          data: {
            username: this.form.username,
            password: this.form.password
          },
          success: (res) => {
            if (res.statusCode === 200) {
              resolve({ success: true, data: res.data })
            } else {
              resolve({ success: false, message: res.data.message || '请求失败' })
            }
          },
          fail: (error) => {
            reject(error)
          }
        })
      })
    }
  }
}
</script>

<style scoped>
.login-container {
  padding: 40rpx;
}

.u-form {
  margin-bottom: 40rpx;
}
</style>