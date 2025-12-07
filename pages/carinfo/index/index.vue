<template>
	<view class="content">
		<view class="box">
			<view class="icon-box" @click="page('jb')">
				<u-image src="/static/img/1.png" width="150px" height="150px"></u-image>
				<view class="icon-text">基本信息</view>
			</view>
			<view class="icon-box" @click="page('cs')">
				<u-image src="/static/img/2.png" width="150px" height="150px"></u-image>
				<view class="icon-text">车身信息</view>
			</view>
			<view class="icon-box" @click="page('ddj')">
				<u-image src="/static/img/3.png" width="150px" height="150px"></u-image>
				<view class="icon-text">电动机信息</view>
			</view>
		</view>
		<view class="box">
			<view class="icon-box" @click="page('dp')">
				<u-image src="/static/img/4.png" width="150px" height="150px"></u-image>
				<view class="icon-text">地盘/转向信息</view>
			</view>
			<view class="icon-box" @click="page('dc')">
				<u-image src="/static/img/5.png" width="150px" height="150px"></u-image>
				<view class="icon-text">电池信息</view>
			</view>
			<view class="icon-box" @click="page('cl')">
				<u-image src="/static/img/6.png" width="150px" height="150px"></u-image>
				<view class="icon-text">车辆/制动信息</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return {
			}
		},
		methods:{
			page(pageName) {
				const fullUrl = `/pages/carinfo/item/${pageName}`;
				
				console.log('跳转到:', fullUrl);
				
				uni.navigateTo({
					url: fullUrl,
					fail: (error) => {
						console.error('页面跳转失败:', error);
					}
				});
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
		background-image: url(/static/img/image_bg.png);
		background-size: cover;
		background-position: center;
		background-repeat: no-repeat;
	}
	.box{
		flex: 1;
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
		padding: 20px 0;
	}
	.icon-box{
		display: flex; 
		flex-direction: column; 
		justify-content: center; 
		align-items: center; 
		height: auto;
		padding: 10px;
		border-radius: 10px;
		transition: all 0.3s ease;
		cursor: pointer;
	}
	.icon-box:hover{
		background-color: rgba(255, 255, 255, 0.1);
		transform: translateY(-5px);
	}
	.icon-box:active{
		transform: translateY(-2px);
	}
	.icon-text{
		font-size: 16px; 
		font-weight: 400; 
		margin-top: 10px;
		text-align: center;
		height: auto;
		color: #333;
	}
</style>