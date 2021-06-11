<template>
  <div>
    establish
    <img src="../../assets/logo.png">
    <h1>{{ msg }}</h1>
    <div v-html="msg"></div>
    <!--<router-view/>-->
    <hello></hello>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        msg: '欢迎来到菜鸟教程！'
      }
    }
  }
</script>

<style>
</style>
