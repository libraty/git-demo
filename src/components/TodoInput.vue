<template>
  <div class="todo-input-section">
    <input 
      type="text" 
      class="todo-input" 
      placeholder="添加新任务..." 
      disabled
    />
    <button class="todo-add-btn" disabled>添加</button>
  </div>
</template>

<script setup>
</script>

<style scoped>
.todo-input-section {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.todo-input {
  flex: 1;
  padding: 12px 16px;
  border: 2px solid #e0e0e0;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s;
  outline: none;
}

.todo-input:focus {
  border-color: #667eea;
}

.todo-add-btn {
  padding: 12px 24px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  cursor: pointer;
  transition: opacity 0.3s;
}

.todo-add-btn:hover {
  opacity: 0.9;
}
</style>
