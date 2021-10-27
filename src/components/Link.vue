<template>
  <div class="Link">
    <img class="icon" src="../assets/link.png"/>
    <p>
      {{ name }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'Link',
  props: {
    name: String,
  },
}
</script>

<style scoped>
.Link {
  display: flex;
  align-content: left;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}
</style>