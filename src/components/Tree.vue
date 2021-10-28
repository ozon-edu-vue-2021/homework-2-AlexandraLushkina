<template>
  <div class="tree" :style="cssProps">
    <Directory v-if="node.type=='directory'" :value="showContent" :name="node.name" :hasContent="hasContent" @toggle="toggle"/> 
    <File v-else :name="node.name" :type="node.type" />
    <div v-if="hasContent" v-show="showContent">
      <Tree
        v-for="child in node.contents"
        :key="child.name"
        :node="child"
        :nestingLevel="nestingLevel + 10"
      />
    </div>
  </div>
</template>

<script>
import Directory from './Directory';
import File from './File';

  export default {
    components: {
      Directory,
      File,
    },
    name: 'Tree',
    props: {
      node: Object,
      nestingLevel: {
        type: Number,
        default: 0,
      }
    },
    data() {
      return {
        showContent: false,
      }
    },
    computed: {
      cssProps() {
        return {
          'margin-left': `${this.nestingLevel}px`,
        }
      },
      hasContent() {
        const {contents} = this.node;
        return contents && contents.length > 0;
      }
    },
    methods: {
      toggle(show) {
        this.showContent = show;
      }
    }
  }
</script>

<style scoped>
pre {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
