<template>
	<view class="content">
		<view>
			<u--image
				:showLoading="true"
				src="/static/img/back.png"
				width="50px"
				height="50px"
				class="backimg"
				@click="back"
			></u--image>
		</view>
		<view class="firstitem">
			<u-text bold text="长宽高" style="margin-left: 10rpx;"></u-text>
			<u-text text="4750mm*182lmm*1624mm" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text  bold text="轴距" style="margin-left: 10rpx;"></u-text>
			<u-text text="2890mm" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="前后轮距" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="1636mm/1636mm" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="整备质量" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="1636kg" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="后备厢容积" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="1636L" align=right bold style="margin-right: 10rpx;"></u-text>
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
			async back(){
				uni.navigateTo({
					url:'/pages/carinfo/index/index'
				})
			}
		},
}
</script>

<style>
@import '/pages/carinfo/item/item.css';
</style>