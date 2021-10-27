<template>
  <div class="Directory">
    <img class="icon" src="../assets/dir.png"/>
    <p>
      {{ name }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'Directory',
  props: {
    name: String,
  }
}
</script>

<style scoped>
.Directory {
  display: flex;
  align-content: left;
}
.icon {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}
</style>
