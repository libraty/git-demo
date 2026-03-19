<script setup>
</script>

<template>
  <div class="todo-app">
    <div class="todo-container">
      <h1 class="todo-title">To-Do List</h1>

      <div class="todo-input-section">
        <input type="text" class="todo-input" placeholder="添加新任务..." disabled />
        <button class="todo-add-btn" disabled>添加</button>
      </div>

      <div class="todo-filters">
        <button class="filter-btn active">全部</button>
        <button class="filter-btn">待完成</button>
        <button class="filter-btn">已完成</button>
      </div>

      <ul class="todo-list">
        <li class="todo-item">
          <div class="todo-item-content">
            <input type="checkbox" class="todo-checkbox" disabled />
            <span class="todo-text">示例任务 1</span>
          </div>
          <button class="todo-delete-btn" disabled>删除</button>
        </li>
        <li class="todo-item">
          <div class="todo-item-content">
            <input type="checkbox" class="todo-checkbox" disabled />
            <span class="todo-text">示例任务 2</span>
          </div>
          <button class="todo-delete-btn" disabled>删除</button>
        </li>
        <li class="todo-item">
          <div class="todo-item-content">
            <input type="checkbox" class="todo-checkbox" disabled />
            <span class="todo-text">示例任务 3</span>
          </div>
          <button class="todo-delete-btn" disabled>删除</button>
        </li>
      </ul>

      <div class="todo-footer">
        <span class="todo-count">共 3 个任务</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.todo-app {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 40px 20px;
  box-sizing: border-box;
}

.todo-container {
  max-width: 600px;
  margin: 0 auto;
  background: white;
  border-radius: 16px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  padding: 40px;
}

.todo-title {
  text-align: center;
  color: #333;
  margin-bottom: 30px;
  font-size: 2.5rem;
}

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

.todo-list {
  list-style: none;
  padding: 0;
  margin: 0 0 30px 0;
}

.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  background: #f8f9fa;
  border-radius: 8px;
  margin-bottom: 10px;
  transition: background 0.3s;
}

.todo-item:hover {
  background: #f0f1f2;
}

.todo-item-content {
  display: flex;
  align-items: center;
  gap: 12px;
  flex: 1;
}

.todo-checkbox {
  width: 20px;
  height: 20px;
  cursor: pointer;
  accent-color: #667eea;
}

.todo-text {
  font-size: 1rem;
  color: #333;
}

.todo-delete-btn {
  padding: 6px 12px;
  background: #ff6b6b;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 0.85rem;
  cursor: pointer;
  transition: background 0.3s;
}

.todo-delete-btn:hover {
  background: #ee5a5a;
}

.todo-footer {
  text-align: center;
  color: #999;
  font-size: 0.9rem;
}
</style>
