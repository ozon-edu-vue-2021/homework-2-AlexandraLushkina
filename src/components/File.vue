<template>
  <div :class="[{ 'selected': selected }, 'file-item']" @click="selectLink">
    <img class="icon" :src="iconSource"/>
    <p >
      {{ name }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'FileItem',
  props: {
    name: String,
    type: String,
  },
  data() {
    return {
      selected: false,
    }
  },
  computed: {
    iconSource() {
      return this.type == 'file' ? require('../assets/file.png') : require('../assets/link.png');
    }
  },
  methods: {
    selectLink() {
      this.selected = !this.selected;
    }
  }
}
</script>

<style scoped>
.file-item {
  display: flex;
  align-content: left;
  width: max-content;
  border-radius: 5px;
  padding-right: 10px;
  margin-bottom: 5px;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 5px;
  align-self: center;
}
.file-item.selected {
  background-color: #c8c8c8;
}
</style>