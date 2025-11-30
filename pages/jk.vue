<template>
	<view class="container">
		<view class="health-status">健康状态</view>
		
		<!-- 固定横向布局 -->
		<view class="health-cards-fixed">
			<!-- 血糖板块 -->
			<view class="health-card-fixed">
				<view class="card-main-fixed">
					<view class="left-section">
						<u--image class="card-icon" showLoading="true" src="/static/images/xuetang.png" width="100rpx" height="100rpx"></u--image>
						<view class="title-content">
							<view class="title-row">
								<u--text class="card-title" bold="true" size="18px" text="血糖"></u--text>
								<u-tag class="fee-tag" text="付费项目" type="error" size="mini" plain @click="fufei"></u-tag>
							</view>
							<u--text color="#bdc2bd" size="16px" text="2025-11-26" class="time-text"></u--text>
						</view>
					</view>
					<view class="right-section">
						<view class="value-unit">
							<u--text bold="true" size="20px" text="5.9"></u--text>
							<u--text color="#bdc2bd" size="14px" text="mmol/L" class="unit"></u--text>
						</view>
					</view>
				</view>
				<view class="card-footer-fixed">
					<u-tag text="‎‎‎‎ㅤ正常‎‎‎‎ㅤ" type="success" bgColor="#d4f5ea" borderColor="#f5fff0" size="mini" plain @click="zhengchang"></u-tag>
				</view>
			</view>

			<!-- 血压板块 -->
			<view class="health-card-fixed">
				<view class="card-main-fixed">
					<view class="left-section">
						<u--image class="card-icon" showLoading="true" src="/static/images/xueya.png" width="100rpx" height="100rpx"></u--image>
						<view class="title-content">
							<view class="title-row">
								<u--text class="card-title" bold="true" size="18px" text="血压"></u--text>
								<u-tag class="fee-tag" text="付费项目" type="error" size="mini" plain @click="fufei"></u-tag>
							</view>
							<u--text color="#bdc2bd" size="16px" text="2025-11-26" class="time-text"></u--text>
						</view>
					</view>
					<view class="right-section">
						<view class="value-unit">
							<u--text bold="true" size="20px" text="107/67"></u--text>
							<u--text color="#bdc2bd" size="14px" text="mmHg" class="unit"></u--text>
						</view>
					</view>
				</view>
				<view class="card-footer-fixed">
					<u-tag text="‎‎‎‎ㅤ异常‎‎‎‎ㅤ" type="error" borderColor="#fef0f0" bgColor="#fef0f0" size="mini" plain @click="yichang"></u-tag>
				</view>
			</view>

			<!-- 心率板块 -->
			<view class="health-card-fixed">
				<view class="card-main-fixed">
					<view class="left-section">
						<u--image class="card-icon" showLoading="true" src="/static/images/xinglv.png" width="100rpx" height="100rpx"></u--image>
						<view class="title-content">
							<view class="title-row">
								<u--text class="card-title" bold="true" size="18px" text="心率"></u--text>
							</view>
							<u--text color="#bdc2bd" size="16px" text="2025-11-26" class="time-text"></u--text>
						</view>
					</view>
					<view class="right-section">
						<view class="value-unit">
							<u--text bold="true" size="20px" text="54"></u--text>
							<u--text color="#bdc2bd" size="14px" text="次/每分钟" class="unit"></u--text>
						</view>
					</view>
				</view>
				<view class="card-footer-fixed">
					<u-tag text="‎‎‎‎ㅤ异常‎‎‎‎ㅤ" type="error" size="mini" borderColor="#fef0f0" bgColor="#fef0f0" plain @click="yichang"></u-tag>
				</view>
			</view>

			<!-- 体温板块 -->
			<view class="health-card-fixed">
				<view class="card-main-fixed">
					<view class="left-section">
						<u--image class="card-icon" showLoading="true" src="/static/images/tiwen.png" width="100rpx" height="100rpx"></u--image>
						<view class="title-content">
							<view class="title-row">
								<u--text class="card-title" bold="true" size="18px" text="体温"></u--text>
							</view>
							<u--text color="#bdc2bd" size="16px" text="2025-11-26" class="time-text"></u--text>
						</view>
					</view>
					<view class="right-section">
						<view class="value-unit">
							<u--text bold="true" size="20px" text="37.2"></u--text>
							<u--text color="#bdc2bd" size="14px" text="℃" class="unit"></u--text>
						</view>
					</view>
				</view>
				<view class="card-footer-fixed">
					<u-tag text="‎‎‎‎ㅤ正常‎‎‎‎ㅤ" type="success" bgColor="#d4f5ea" borderColor="#f5fff0" size="mini" plain @click="zhengchang"></u-tag>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	methods: {
		fufei() {
			this.$u.toast('此项目为付费项目！')
		},
		zhengchang() {
			this.$u.toast('当前项目状态正常')
		},
		yichang() {
			this.$u.toast('当前项目状态异常！请关注！')
		}
	},
}
</script>

<style scoped>
.container {
	background-color: #f5f4f9;
	padding: 30rpx;
	min-height: 100vh;
	box-sizing: border-box;
}

.health-status {
	font-size: 40rpx;
	color: #373c46;
	margin-bottom: 40rpx;
	font-weight: bold;
	text-align: left;
}

/* 固定布局容器 */
.health-cards-fixed {
	display: flex;
	flex-direction: column;
	gap: 20rpx;
	width: 100%;
}

/* 固定卡片样式 */
.health-card-fixed {
	background-color: #FFFFFF;
	border-radius: 20rpx;
	padding: 30rpx;
	width: 100%;
	box-sizing: border-box;
	box-shadow: 0 2rpx 12rpx rgba(0, 0, 0, 0.08);
}

/* 卡片主要内容区域 */
.card-main-fixed {
	display: flex;
	justify-content: space-between;
	align-items: flex-start;
	margin-bottom: 20rpx;
	width: 100%;
}

/* 左侧区域 - 重新布局 */
.left-section {
	display: flex;
	align-items: flex-start;
	gap: 20rpx;
	flex: 1;
}

.card-icon {
	flex-shrink: 0;
}

/* 新的标题和时间布局 */
.title-content {
	display: flex;
	flex-direction: column;
	gap: 8rpx;
}

.title-row {
	align-items: center;
	gap: 15rpx;
}

.card-title {
	white-space: nowrap;
}

.fee-tag {
	flex-shrink: 0;
}

.time-text {
	white-space: nowrap;
}

/* 右侧数值区域 */
.right-section {
	display: flex;
	justify-content: flex-end;
	align-items: flex-start;
	flex-shrink: 0;
}

.value-unit {
	display: flex;
	align-items: baseline;
	gap: 1rpx;
}

.unit {
	white-space: nowrap;
	margin-left: 0;
}

/* 底部区域 - 只保留状态标签 */
.card-footer-fixed {
	display: flex;
	justify-content: flex-end;
	align-items: center;
	width: 100%;
}

/* 确保布局在任何屏幕尺寸下都保持一致 */
@media (max-width: 750rpx) {
	.health-card-fixed {
		padding: 25rpx;
	}
	
	.card-main-fixed {
		margin-bottom: 15rpx;
	}
	
	.left-section {
		gap: 15rpx;
	}
	
	.title-row {
		gap: 12rpx;
	}
	
	.title-content {
		gap: 6rpx;
	}
}

@media (max-width: 600rpx) {
	.container {
		padding: 20rpx;
	}
	
	.health-status {
		font-size: 36rpx;
		margin-bottom: 30rpx;
	}
	
	.health-cards-fixed {
		gap: 15rpx;
	}
	
	.health-card-fixed {
		padding: 20rpx;
	}
	
	.card-main-fixed {
		flex-direction: row;
		align-items: flex-start;
	}
	
	.value-unit {
		flex-direction: row;
		align-items: baseline;
		gap: 1rpx;
	}
	
	/* 在小屏幕上调整图标大小 */
	.card-icon {
		width: 50rpx;
		height: 50rpx;
	}
}

/* 超小屏幕保护 */
@media (max-width: 400rpx) {
	.title-row {
		flex-direction: column;
		align-items: flex-start;
		gap: 8rpx;
	}
	
	.card-main-fixed {
		flex-wrap: wrap;
	}
	
	.right-section {
		margin-top: 10rpx;
		width: 100%;
		justify-content: flex-start;
	}
	
	/* 在超小屏幕上调整图标大小 */
	.card-icon {
		width: 45rpx;
		height: 45rpx;
	}
}

/* 防止内容溢出 */
.card-title,
.time-text,
.unit {
	overflow: visible;
	text-overflow: clip;
	white-space: nowrap;
}

/* 固定布局保护 */
.health-cards-fixed,
.health-card-fixed,
.card-main-fixed,
.card-footer-fixed {
	min-width: 300rpx;
}

/* 特别针对单位文本的保护 */
.unit {
	min-width: auto;
	max-width: none;
}
/* 标题行布局调整 */
.title-row {
	display: flex;
	align-items: center;
	gap: 15rpx;
	flex-wrap: nowrap;
}

.card-title {
	white-space: nowrap;
	flex-shrink: 0;
}

.fee-tag {
	flex-shrink: 0;
	white-space: nowrap;
}

.time-text {
	white-space: nowrap;
	margin-top: 8rpx;
}
</style>