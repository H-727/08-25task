<template>
  <div id="app">
    <span v-for="itme in arr" :key="itme">
      <input type="checkbox" :value="itme" v-model="happy" />
      <span> {{ itme }}</span>
    </span>
    <ul>
      <li v-for="(itme, index) in happy" :key="index">{{ itme }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: ["科幻", "喜剧", "动漫", "冒险", "科技", "军事", "娱乐", "奇闻"],
      happy: [],
    };
  },
};
</script>
<style lang="less"></style>
