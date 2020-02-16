<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{msg}}</p>
  </div>
</template>

<script>
import store from '@/store/index'
export default {
  name: 'About',
  store,
  /* 一个组件的 data 选项必须是一个函数 */
  data: function () {
    return {
      msg: store.state.count
    }
  }
}
</script>
