<template>
  <div>
    <!--   订单状态导航 -->
    <van-tabs v-model:active="active" :swipeable="true" @click="onClickTab" animated>
      <van-tab v-for="data in stateEnum" :title="data.k" :key="data.v">
        {{ data.k }}
      </van-tab>
    </van-tabs>
  </div>
</template>

<script>
export default {
  name: "orderState",
  props: {
    state: String
  },
  data() {
    return {
      active: 0,
      stateEnum: [
        {k: "全部", v: 0},
        {k: "未支付", v: 1},
        {k: "待发货", v: 2},
        {k: "待收获", v: 3},
        {k: "待评价", v: 4},
        {k: "已完成", v: 5}
      ]
    }
  },
  methods: {
    onClickTab(v) {
      console.log(v)
    }
  },
  mounted() {
    console.log(this.state)
    this.active = parseInt(this.state)
  }
}
</script>

<style scoped>

</style>