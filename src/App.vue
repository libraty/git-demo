<script setup>
import { ref } from 'vue'
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoFilters from './components/TodoFilters.vue'
import TodoList from './components/TodoList.vue'
import TodoItem from './components/TodoItem.vue'
import TodoFooter from './components/TodoFooter.vue'
import ConfirmDialog from './components/ConfirmDialog.vue'

const tasks = ref([
  { id: 1, text: '示例任务 1', completed: false },
  { id: 2, text: '示例任务 2', completed: false },
  { id: 3, text: '示例任务 3', completed: false }
])

const newTask = ref('')

const deleteTaskId = ref(null)
const isDialogVisible = ref(false)

const addTask = () => {
  if (newTask.value.trim()) {
    tasks.value.push({
      id: Date.now(),
      text: newTask.value.trim(),
      completed: false
    })
    newTask.value = ''
  }
}

const requestRemoveTask = (id) => {
  deleteTaskId.value = id
  isDialogVisible.value = true
}

const confirmRemoveTask = () => {
  if (deleteTaskId.value !== null) {
    tasks.value = tasks.value.filter(task => task.id !== deleteTaskId.value)
    deleteTaskId.value = null
  }
  isDialogVisible.value = false
}

const cancelRemoveTask = () => {
  deleteTaskId.value = null
  isDialogVisible.value = false
}

const toggleTask = (id) => {
  const task = tasks.value.find(task => task.id === id)
  if (task) {
    task.completed = !task.completed
  }
}
</script>

<template>
  <div class="todo-app">
    <div class="todo-container">
      <TodoHeader />
      <TodoInput @add-task="addTask" v-model="newTask" @enter="addTask" />
      <TodoFilters />
      <TodoList>
        <TodoItem v-for="task in tasks" :key="task.id" :text="task.text" @click:checkbox="toggleTask(task.id)"
          @click:delete="requestRemoveTask(task.id)" />
      </TodoList>
      <TodoFooter :count="tasks.length" />
    </div>
    <ConfirmDialog v-model:visible="isDialogVisible" title="确认删除" message="确定要删除这个任务吗？真的吗此操作不可撤销。"
      @confirm="confirmRemoveTask" @cancel="cancelRemoveTask" />
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
</style>
