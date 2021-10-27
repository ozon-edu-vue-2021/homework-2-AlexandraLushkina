<template>
  <div class="File">
    <img class="icon" src="../assets/file.png"/>
    <p>
      {{ name }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'File',
  props: {
    name: String,
  }
}
</script>

<style scoped>
.File {
  display: flex;
  align-content: left;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}
</style>