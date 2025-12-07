<template>
	<view class="content">
		<view class="card">
			<u-input v-model="mobile" label="手机号" placeholder="请填写手机号"></u-input>			
		</view>
		<view class="card">
			<u-input v-model="password" label="密码" placeholder="请填写密码" password:true></u-input>
		</view>
		<u-button type="primary" style="800rpx" @click="up()" :loading="loading">登录</u-button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				mobile:'',
				password:'',
			}
		},
		methods:{
			async up(){
				this.loading = true
				try {
				    // 向 MySQL 数据库写入数据
				    const result = await this.saveToDatabase()
				    
				    if (result.success) {
				      this.$u.toast(result.message)
				      // 清空表单
				      this.mobile = ''
				      this.password = ''
				    } else {
				      this.$u.toast('登录失败：' + result.message)
				    }
				  } catch (error) {
				    console.error('登录错误:', error)
				    this.$u.toast('登录出错，请重试')
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
			      url: 'http://47.122.42.177:3000/api/users/login', // 替换为你的实际 API 地址
			      method: 'POST',
			      data: {
			        username: this.mobile,
			        password: this.password
			      },
				  timeout:10000,
			      success: (res) => {
			        if (res.statusCode === 200) {
			          resolve({ success: true, message: res.data.message })
					  uni.showToast({
					  	title:'登录成功',
						duration:3000,
						icon:'success'
					  })
					  uni.navigateTo({
						  url:'/pages/carinfo/index/index'
					  })
			        } else {
			          resolve({ success: false, message: res.data.message || '请求失败' })
			        }
					console.log(res.data)
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

<style>
	.content{
		width: 100vw;
		height: 100vh;
		display: flex;
		flex-direction: column;
		background-image:url(/static/img/image_bg.png)
	}
	.card{
		background-color: #FFFFFF;
		border-radius: 20rpx;
		height: 100rpx;
		display: flex;
		align-items: center;
		margin: 40rpx;
	}
</style>