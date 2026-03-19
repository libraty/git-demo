<template>
  <div class="todo-filters">
    <button class="filter-btn active">全部!!!</button>
    <button class="filter-btn">待完成</button>
    <button class="filter-btn">已完成</button>
  </div>
</template>

<script setup>
</script>

<style scoped>
.todo-filters {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
  justify-content: center;
}

.filter-btn {
  padding: 8px 16px;
  border: 2px solid #e0e0e0;
  border-radius: 20px;
  background: white;
  color: #666;
  cursor: pointer;
  transition: all 0.3s;
}

.filter-btn.active {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-color: transparent;
}
</style>
