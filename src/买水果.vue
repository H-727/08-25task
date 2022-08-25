<template>
  <div id="app">
    <table>
      <caption>
        欢迎光临_vue开发的收银系统_水果店
      </caption>
      <tr>
        <td>苹果10元/斤，折扣8折</td>
      </tr>
      <tr>
        <td>请输入你要的斤数<input type="text" v-model.number="num" /></td>
      </tr>
      <tr>
        <td><button @click="sum">结账买单~</button></td>
      </tr>
      <tr>
        <td>
          结账单：总价：{{ num1 }}￥元 折后价{{ num2 }}￥元 省了{{
            num1 - num2
          }}￥元
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num: "",
      num1: 0,
      num2: 0,
    };
  },
  methods: {
    sum() {
      this.num1 = 10 * this.num;
      this.num2 = this.num1 * 0.8;
    },
  },
};
</script>
<style lang="less"></style>
