<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/> 
    <HiWorld/>
    <Article/>
    <Column/>
    <Review/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import HiWorld from './components/HiWorld'
import Article from './components/article'
import Column from './components/column'
import Review from './components/review'
export default {
  name: 'App',
  components: {
    HelloWorld,
    HiWorld,
    Article,
    Column,
    Review
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
