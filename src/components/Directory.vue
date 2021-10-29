<template>
  <div class="directory-item">
    <img class="icon" src="../assets/dir.png" @click="toggle"/>
    <p @click="toggle">
      {{ name }}
    </p>
    <img v-if="hasContent" class="toggle-button" :src="toggleIcon" @click="toggle" @keypress="toggle"/>
  </div>
</template>

<script>
export default {
  name: 'DirectoryItem',
  data() {
    return {
      showContent: this.value,
    }
  },
  props: {
    name: String,
    hasContent: Boolean,
    value: Boolean,
  },
  computed: {
    toggleIcon() {
      return this.showContent ? require("../assets/minus.svg") : require("../assets/plus.svg");
    }
  },
  methods: {
    toggle() {
      this.showContent = !this.showContent;
      this.$emit('toggle', this.showContent);
    },
  }
}
</script>

<style scoped>
.directory-item {
  display: flex;
  align-content: left;
  cursor: pointer;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 10px;
  align-self: center;
}
.toggle-button {
  margin-left: 10px;
  width: 20px;
}
</style>
