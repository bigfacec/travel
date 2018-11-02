<template>
  <div id="app">
    <test id="">
      <input type="text">
    </test>
  </div>
</template>

<script>
import test from '@/components/test3'
export default {
  name: 'App',
  components:{
      test : test
  }
}
</script>

<style>
#app {
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
}
</style>
