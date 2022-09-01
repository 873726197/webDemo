<template>
  <div id="app">
    <ul>
      <li v-for="(item , index) in arr" :key="index">
        {{ item }}
        <button @click="fn1(index)">删除</button>
      </li>
      <hr>
    </ul>
    <button @click="fn">点击生成随机数</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [Math.floor(Math.random() * 100), Math.floor(Math.random() * 100)],
    }

  },
  methods: {
    fn() {
      let num = Math.floor(Math.random() * 100)
      this.arr.push(num)
    },
    fn1(idx) {
      this.arr.splice(idx, 1)
    }
  },
}
</script>