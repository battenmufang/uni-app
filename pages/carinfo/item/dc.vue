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
			<u-text bold text="电池容量" style="margin-left: 10rpx;"></u-text>
			<u-text text="200kw" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text  bold text="电池品牌" style="margin-left: 10rpx;"></u-text>
			<u-text text="松下" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="百公里耗电量" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="50Kw/100Km" align=right bold style="margin-right: 10rpx;"></u-text>
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