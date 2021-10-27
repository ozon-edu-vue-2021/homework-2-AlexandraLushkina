<template>
    <div class="tree" v-show="propsShow">
        <div v-for="item in src" :key="item.name" :style="cssProps" v-on:click="toggleShow">
          <div class="node" v-if="item.type=='directory'">
            <Directory :name="item.name" />
            <Tree :key="item.name" :src="item.contents" :nestingLevel="nestingLevel+1" :propsShow="isShow"/>
          </div>
          <div class="node" v-else-if="item.type=='file'">
            <File :name="item.name"/>
          </div>
          <div class="node" v-else-if="item.type=='link'">
            <Link :name="item.name"/>
          </div>
        </div>
    </div>
</template>

<script>
  import Directory from './Directory.vue';
  import File from './File.vue';
  import Link from './Link.vue';

  export default {
    name: 'Tree',
    components: {
      Directory,
      File,
      Link,
    },
    props: {
      src: Array,
      nestingLevel: Number,
      propsShow: Boolean,
    },
    computed: {
      cssProps() {
        return {
          '--tabs': (this.nestingLevel * 10).toString() + 'px',
        }
      },
    },
    data: function() {
      return {
        isShow: false,
      }
    },
    methods: {
      toggleShow() {
        console.log(this.isShow)
        this.isShow = !this.isShow;
      }
    }
  }
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
pre {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
.node {
  margin-left: var(--tabs);
}
</style>
