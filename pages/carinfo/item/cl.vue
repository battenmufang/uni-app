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
			<u-text bold text="前后制动器类型" style="margin-left: 10rpx;"></u-text>
			<u-text text="通风盘式/通风盘式" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text  bold text="驻车制动类型" style="margin-left: 10rpx;"></u-text>
			<u-text text="电子驻车" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="前轮胎规格" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="255/45 R19" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="后轮胎规格" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="255/45 R19" align=right bold style="margin-right: 10rpx;"></u-text>
		</view>
		<view class="item">
			<u-text text="前轮胎规格" bold style="margin-left: 10rpx;"></u-text>
			<u-text text="铝合金" align=right bold style="margin-right: 10rpx;"></u-text>
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