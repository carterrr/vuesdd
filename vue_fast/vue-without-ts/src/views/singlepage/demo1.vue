<template>
  <div class="info">
    <!-- 代码规范性  每个v-for都要一个key -->
    <!-- js中 0 == '' 是true的  因此 current !== ''可以避免 第一项默认被选中 -->
    <ul>
      <li v-for="(item,index) in lists" :key="index"
      @click="choose(index)"
      :class="{active : index == current && current !== ''}">
      <p>{{item}}</p>
    </li>
    </ul>
    <button type="button" @click="add(current)">添加后长度 {{targetlength}}</button>
    <ul>
      <li v-for="(itee,indea) in target" :key="indea">
        {{itee}}
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Info',
  data: function () {
    return {
      current: '',
      lists: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      target: []
    }
  },
  methods: {
    choose (index) {
      console.log(index)
      this.current = index
    },
    add: function (current) {
      /* js中数组方法没有add 只有
      arrayObject.push(newelement1,newelement2,....,newelementX)
      arrayObject.unshift(newelement1,newelement2,....,newelementX)
      arrayObject.splice(index,howmany,item1,.....,itemX) */
      if (current !== '') {
        this.target.push(current)
      }
      this.current = ''
    }
  },
  computed: {
    /* 计算属性可直接引用  不必在data中在定义一次 */
    targetlength: function () {
      return this.target.length
    }
  }
}
</script>
<style scoped>
li.active {
  background : green;
}
</style>
