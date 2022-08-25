<template>
  <div id="app">
    <span v-for="itme in arr" :key="itme">
      <input type="checkbox" :value="itme" v-model="happy" />
      <span> {{ itme }}</span>
    </span>
    <div>你选中的元素的和为：{{ sum }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      happy: [],
    };
  },
  computed: {
    sum() {
      if (this.happy.length === 0) return 0;
      return this.happy.reduce((num, itme) => num + itme);
    },
  },
};
</script>
<style lang="less"></style>
