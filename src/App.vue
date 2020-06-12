<!--
 * @Descripttion: 
 * @version: 
 * @Author: JohnsonZzp
 * @Date: 2020-06-12 15:23:07
 * @LastEditors: JohnsonZzp
 * @LastEditTime: 2020-06-12 15:30:58
--> 
<template>
  <div id="app">
    <img src="./assets/logo.png">
    <test2/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import test2 from './components/test2'
import test from './components/test'

export default {
  name: 'App',
  components: {
    HelloWorld,
    test,
    test2
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
