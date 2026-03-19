<template>
  <ul class="todo-list">
    <slot />
  </ul>
</template>

<script setup>
</script>

<style scoped>
.todo-list {
  list-style: none;
  padding: 0;
  margin: 0 0 30px 0;
}
</style>
