<template>
  <div class="todo-footer">
    <span class="todo-count">共 {{ count }} 个任务</span>
  </div>
</template>

<script setup>
defineProps({
  count: {
    type: Number,
    default: 0
  }
})
</script>

<style scoped>
.todo-footer {
  text-align: center;
  color: #999;
  font-size: 0.9rem;
}
</style>
