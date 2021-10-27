<template>
  <div id="app">
    <Tree :src="src" :nestingLevel="1" :propsShow="propsShow"/>
  </div>
</template>

<script>
import Tree from './components/Tree.vue';
import NODE_MODULES from '../public/static/testFile.json';

export default {
  name: 'App',
  components: {
    Tree
  },
  data() {
    return {
      src: [NODE_MODULES],
      propsShow: true,
    }
  }
}
</script>

<style>
#app {
  display: block;
  margin-top: 40px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
