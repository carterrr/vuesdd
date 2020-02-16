<template>
  <div class="info">
    <p>info component</p>
    <button type="button" @click="add()">点击增加</button>
  </div>
</template>

<script>
// @ is an alias to /src
import store from '@/store/index'

export default {
  name: 'Info',
  store,
  data: function () {
    return {
      msg: 'testDebugger'
    }
  },
  /* 调试方法 7 绑定本component到全局变量中 mounted表示本component加载完成后执行 */
  mounted: function () {
    window.vue = this
  },
  methods: {
    add: function () {
      /* 7种调试方法 */
      console.log('add method be invoked')/* 调试方法1 */
      console.error('error occured when invoking add method ')/* 调试方法2 */
      alert('add method be invoked') /*  调试方法3 注： alert方法是阻塞式的 点了确定之后程序才会往后进行 */
      debugger /* 调试方法 4 属性调试 ：在控制台输入this.msg 打印即可  */
      /* 不加() 仅仅写上方法名 */
      store.commit('increase')
    },
    /* 调试方法 5 方法调试 ：在控制台输入this.output() 打印即可 */
    output: function () {
      console.log(this.msg)
    }
  }
  /* 调试方法 6 vuex插件调试 ：XHR  slow3G */
}
</script>
