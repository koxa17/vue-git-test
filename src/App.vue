<template>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <h1>Title test</h1>
  <h1>Title test</h1>
  <h1>Title test</h1>
  <h1>Title test</h1>
  <h1>Title test</h1>
  <h1>Title test</h1>
  <h1>Title test</h1>
  <test-comp />
  <servise-list/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TestComp from "@/components/TestComp";
import ServiseList from "@/components/ServiseList";

export default {
  name: 'App',
  components: {
    ServiseList,
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
