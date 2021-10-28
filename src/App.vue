<template>
  <div id="app">
    <Tree v-for="node in src" :key="node.name" :node="node"/>
  </div>
</template>

<script>
import Tree from './components/Tree';
import NODE_MODULES from '../public/static/testFile.json';

export default {
  name: 'App',
  components: {
    Tree
  },
  data() {
    return {
      src: [NODE_MODULES],
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
