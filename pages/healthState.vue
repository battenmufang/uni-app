<template>
  <view class="container">
    <view class="header">
      <text class="title">健康状态</text>
    </view>

    <view class="card-list">
      <view class="card" v-for="(item, index) in healthData" :key="index">
        <view class="card-left">
          <!-- 图标 -->
          <view class="icon-box" :style="{ background: item.iconBg }">
            <u-icon :name="item.icon" color="#0055ff" size="50"></u-icon>
          </view>
          <!-- 信息 -->
          <view class="info">
            <view class="info-title">
              <text class="name">{{ item.name }}</text>
              <text class="status" :class="item.isFree ? 'free' : 'pay'">
                {{ item.statusText }}
              </text>
            </view>
            <text class="date">{{ item.date }}</text>
          </view>
        </view>

        <!-- 数值 -->
        <view class="card-right">
          <text class="value">
            {{ item.value }}
            <text class="unit">{{ item.unit }}</text>
          </text>
          <view :class="item.isNormal ? 'btn-normal' : 'btn-warning'">
            {{ item.isNormal ? '正常' : '异常' }}
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      healthData: [
        {
          name: '血糖',
          icon: 'star-fill',
          iconBg: 'rgba(255, 255, 255, 0.3)',
          value: '5.9',
          unit: 'mmol/L',
          date: '2025-11-26',
          statusText: '付费项目',
          isNormal: true,
          isFree: false
        },
        {
          name: '血压',
          icon: 'grid-fill',
          iconBg: 'rgba(255, 255, 255, 0.3)',
          value: '107/67',
          unit: 'mmHg',
          date: '2025-11-26',
          statusText: '付费项目',
          isNormal: false,
          isFree: false
        },
        {
          name: '心率',
          icon: 'heart-fill',
          iconBg: 'rgba(255, 255, 255, 0.3)',
          value: '54',
          unit: '次/分钟',
          date: '2025-11-26',
          statusText: '付费项目',
          isNormal: false,
          isFree: true
        },
        {
          name: '体温',
          icon: 'bell-fill',
          iconBg: 'rgba(255, 255, 255, 0.3)',
          value: '37.2',
          unit: '℃',
          date: '2025-11-26',
          statusText: '正常',
          isNormal: true,
          isFree: true
        }
      ]
    }
  },
  methods: {
    // 点击卡片
    handleCardClick(item) {
      console.log('点击了:', item.name)
      uni.showToast({
        title: `查看${item.name}详情`,
        icon: 'none'
      })
    }
  }
}
</script>

<style scoped>
/* 样式与上面相同 */
.container {
  min-height: 100vh;
  background-color: #f5f5f5;
  padding-bottom: 40rpx;
}

.header {
  padding: 40rpx;
  background-color: #f5f5f5;
}

.title {
  font-size: 44rpx;
  font-weight: bold;
  color: #333333;
}

.card-list {
  padding: 20rpx 30rpx;
}

.card {
  border-radius: 20rpx;
  padding: 30rpx;
  margin-bottom: 30rpx;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 8rpx 20rpx rgba(0, 0, 0, 0.1);
  background-color: #ffffff;
}

.card-left {
  display: flex;
  align-items: center;
}

.icon-box {
  width: 100rpx;
  height: 100rpx;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 24rpx;
}

.info {
  display: flex;
  flex-direction: column;
}

.info-title {
  display: flex;

  align-items: center;
  margin-bottom: 8rpx;
}

.name {
  font-size: 32rpx;
  font-weight: bold;
  color: #000000;
  margin-right: 16rpx;
}

.status {
  font-size: 22rpx;
  padding: 4rpx 12rpx;

}

.status.free {
  display: none;
}

.status.pay {
  background-color: rgba(255, 107, 107, 0.8);
  color: #ba3e5f;
}

.date {
  font-size: 24rpx;
  color: rgba(217, 217, 214, 1.0);
}

.card-right {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.value {
  font-size: 39rpx;
  font-weight: bold;
  color: #000000;
  margin-bottom: 16rpx;
}

.unit {
  font-size: 24rpx;
  font-weight: normal;
  color: rgba(197, 202, 204, 1.0);
}

.btn-normal,
.btn-warning {
  padding: 8rpx 24rpx;
  border-radius: 10rpx;
  font-size: 24rpx;
}

.btn-normal {
  background-color: rgba(210, 245, 233, 1.0);
  color: #a4ecd3;
}

.btn-warning {
  background-color: rgba(255, 107, 107, 0.9);
  color: #ba3e5f;
}
</style>