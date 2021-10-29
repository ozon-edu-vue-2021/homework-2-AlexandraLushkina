<template>
  <div id="app">
    <Tree :node="src[0]"/>
  </div>
</template>

<script>
import Tree from './components/Tree';
import src from '../public/static/node_modules.json';

export default {
  name: 'App',
  components: {
    Tree
  },
  data() {
    return {
      src: [src],
    }
  }
}
</script>

<style>
#app {
  display: block;
  margin-top: 40px;
  margin-left: 40px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
