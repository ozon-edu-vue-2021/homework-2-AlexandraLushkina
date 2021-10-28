<template>
  <div class="link-item">
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
}
</script>

<style scoped>
.link-item {
  display: flex;
  align-content: left;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}
</style>