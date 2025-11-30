<template>
  <view class="u-page">
    <u-list @scrolltolower="scrolltolower">
      <u-list-item v-for="(item, index) in indexList" :key="index">
        <u-cell :title="`${jichu}`" :label="`基础费用：${money}元/月`"></u-cell>
      </u-list-item>
    </u-list>
  </view>
</template>

<script>
  export default {
    data() {
      return {
		jichu:"老人生活日常基础需求，伙食、床位、定期换洗床被、送水、督促服药等。",
		money: 2500.00,
        indexList: [],

      };
    },
    onLoad() {
      this.loadmore();
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
    },
  };
</script>