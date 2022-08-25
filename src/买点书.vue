<template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
      <li v-for="(itme, index) in arr" :key="index">
        {{ itme.name }} <button @click="add(index)">买入</button>
      </li>
    </ul>
    <table border="1" width="500" cellspacing="0">
      <tr>
        <th>序号</th>
        <th>书名</th>
        <th>单价</th>
        <th>数量</th>
        <th>合计</th>
      </tr>
      <tr v-for="(itme, index) in arr" :key="index">
        <td>{{ index + 1 }}</td>
        <td>{{ itme.name }}</td>
        <td>{{ itme.price }}</td>
        <td>{{ itme.count }}</td>
        <td>{{ itme.count * itme.price }}</td>
      </tr>
    </table>
    <p>总价格为:{{ print }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          name: "水浒传",
          price: 107,
          count: 0,
        },
        {
          name: "西游记",
          price: 192,
          count: 0,
        },
        {
          name: "三国演义",
          price: 219,
          count: 0,
        },
        {
          name: "红楼梦",
          price: 178,
          count: 0,
        },
      ],
    };
  },
  methods: {
    add(i) {
      this.arr[i].count++;
    },
  },
  computed: {
    print() {
      return this.arr.reduce(
        (sum, itme) => (sum += itme.price * itme.count),
        0
      );
    },
  },
};
</script>
