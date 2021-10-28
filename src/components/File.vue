<template>
  <div class="file-item">
    <img class="icon" src="../assets/file.png"/>
    <p>
      {{ name }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'FileItem',
  props: {
    name: String,
  }
}
</script>

<style scoped>
.file-item {
  display: flex;
  align-content: left;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}
</style>