<template>
  <li class="todo-item">
    <div class="todo-item-content">
      <input 
        type="checkbox" 
        class="todo-checkbox" 
        :checked="completed"
        @click="$emit('click:checkbox')"
      />
      <span class="todo-text">{{ text }}</span>
    </div>
    <button class="todo-delete-btn" @click="$emit('click:delete')">删除</button>
  </li>
</template>

<script setup>
defineProps({
  text: {
    type: String,
    default: ''
  },
  completed: {
    type: Boolean,
    default: false
  }
})

defineEmits(['click:checkbox', 'click:delete'])
</script>

<style scoped>
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
</style>
