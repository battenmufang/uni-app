<template>
	<view class="center-all">
		<view class="center.box">
			<u-text text="根据您填写的身体状态，您的所需的养老机构护理等级为1级"></u-text>
		</view>
		<view class="charts-box">
		    <qiun-data-charts 
		      type="gauge"
		      :opts="opts"
		      :chartData="chartData"
		      :canvas2d="true"
		      canvasId="IMlsnZgUPVOHuAaYuDrVWEJKRPWCvlLB"
		    />
		</view>
		<u-list @scrolltolower="scrolltolower" style="height: 50%;">
		  <u-list-item v-for="(item, index) in indexList" :key="index">
		    <u-cell :title="jichu" :label="`基础费用：${money}元/月`"></u-cell>
		  </u-list-item>
		</u-list>
		<u-button style="width: 95%;" type="primary" size="large" text="智能匹配服务机构"></u-button>
	</view>
</template>

<script>
export default {
	  data() {
	    return {
		  jichu:"老人生活日常基础需求，伙食、床位、定期换洗床被、送水、督促服药等。",
		  money: 2500.00,
		  disabled: true,
		  indexList: [],
	      chartData: {},
	      //您可以通过修改 config-ucharts.js 文件中下标为 ['gauge'] 的节点来配置全局默认参数，如都是默认参数，此处可以不传 opts 。实际应用过程中 opts 只需传入与全局默认参数中不一致的【某一个属性】即可实现同类型的图表显示不同的样式，达到页面简洁的需求。
	      opts: {
	        color: ["#1890FF","#91CB74","#FAC858","#EE6666","#73C0DE","#3CA272","#FC8452","#9A60B4","#ea7ccc"],
	        padding: undefined,
	        title: {
	          name: "一级护理",
	          fontSize: 25,
	          color: "#5aa3d4",
	          offsetY: 0
	        },
	        subtitle: {
	          name: "",
	          fontSize: 15,
	          color: "#1890ff",
	          offsetY: 0
	        },
	        extra: {
	          gauge: {
	            type: "progress",
	            width: 20,
	            labelColor: "#666666",
	            startAngle: 0.75,
	            endAngle: 0.25,
	            startNumber: 0,
	            endNumber: 100,
	            labelFormat: "",
	            splitLine: {
	              fixRadius: -10,
	              splitNumber: 10,
	              width: 15,
	              color: "#FFFFFF",
	              childNumber: 5,
	              childWidth: 12
	            },
	            pointer: {
	              width: 24,
	              color: "auto"
	            }
	          }
	        }
	      }
	    };
	  },
	  onLoad() {
	    this.loadmore();
	  },
	  onReady() {
	    this.getServerData();
	 },
	  methods: {
		scrolltolower() {
		          this.loadmore();
		        },
		loadmore() {
					for (let i = 0; i < 3; i++) {
					this.indexList.push({
					});
				}
		},
	    getServerData() {
	      //模拟从服务器获取数据时的延时
	      setTimeout(() => {
	        //模拟服务器返回数据，如果数据格式和标准格式不同，需自行按下面的格式拼接
	        let res = {
	            categories: [{"value":0.2,"color":"#1890ff"},{"value":0.8,"color":"#2fc25b"},{"value":1,"color":"#f04864"}],
	            series: [
	              {
	                name: "完成率",
	                data: 0.10
	              }
	            ]
	          };
	        this.chartData = JSON.parse(JSON.stringify(res));
	      }, 500);
	    },
	  },
	};
</script>

<style>
	.center-all {
	  display: flex;
	  justify-content: center; /* 水平居中 */
	  align-items: center;     /* 垂直居中 */
	  flex-direction: column;  /* 垂直排列 */
	}
	.center.box{
	  /* 内容样式 */
	  background: white;
	  padding: 40rpx;
	  border-radius: 20rpx;
	  box-shadow: 0 4rpx 20rpx rgba(0,0,0,0.1);
	}
	  /* 请根据实际需求修改父元素尺寸，组件自动识别宽高 */
	.charts-box {
	 width: 100%;
	 height: 300px;
	  }
</style>