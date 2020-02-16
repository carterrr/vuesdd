<template>
  <div class="info">
    <h1>This is an info page</h1>
    <button type="button" @click="add()">add</button>
  </div>
</template>
<script>
import store from '@/store/index';

export default {
  name: 'Info',
  store,
  methods: {
    add() {
      store.commit('add')
    }
  }
}
</script>

<style scoped>

</style>
