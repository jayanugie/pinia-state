<template>
  <div class="task">
    <h3>{{ task.title }}</h3>
    <div>
      <i class="material-icons">delete</i>
      <i class="material-icons">favorite</i>
    </div>
  </div>
</template>

<script>
export default {
  props: ["task"],
};
</script>

<style scoped>
.task {
  display: flex;
  align-items: center;
}
</style>
