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
			<u-text bold text="驱动形式" style="margin-left: 10rpx;"></u-text>
			<u-text text="四驱" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text  bold text="前悬挂类型" style="margin-left: 10rpx;"></u-text>
			<u-text text="双叉臂式独立悬架" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="后悬挂类型" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="多连杆式独立悬架" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="转向助力形式" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="电动助力转向" align=right bold style="margin-right: 10rpx;"></u-text>
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