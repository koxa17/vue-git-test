<template>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <test-comp />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TestComp from "@/components/TestComp";

export default {
  name: 'App',
  components: {
    TestComp,
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
