<template>
  <div class="link-item" @click="selectLink" :style="cssProps">
    <img class="icon" src="../assets/link.png"/>
    <p>
      {{ name }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'LinkItem',
  props: {
    name: String,
  },
  data() {
    return {
      selected: false,
    }
  },
  computed: {
    cssProps() {
      return {
        'background-color': this.selected ? '#c8c8c8' : 'transparent',
      }
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
.link-item {
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
</style>