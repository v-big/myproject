<template>
  <div id="app">
    <!--<test msg="这是新的属性值哟！"></test>-->
    <div>
    <DateFilter ></DateFilter>

      </div>
  </div>
</template>

<script type="es6">
//import test from "./components/Test"
//import users from "./components/Users"
import datefilter from "./components/DateFilter"

export default {
  name: 'App',
  components:{
  datefilter
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
