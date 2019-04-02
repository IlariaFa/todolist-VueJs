<template>
  <div id="app">
<todo></todo>
  </div>
</template>

<script>

import todo from './components/todo.vue';
export default{
  name: 'app',
  components: {
    todo
  }
}

</script>

<style>
  #app{
    font-size:24px;
  }

</style>
