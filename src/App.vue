<script setup>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoFilters from './components/TodoFilters.vue'
import TodoList from './components/TodoList.vue'
import TodoItem from './components/TodoItem.vue'
import TodoFooter from './components/TodoFooter.vue'
</script>

<template>
  <div class="todo-app">
    <div class="todo-container">
      <TodoHeader />
      <TodoInput />
      <TodoFilters />
      <TodoList>
        <TodoItem />
        <TodoItem />
        <TodoItem />
      </TodoList>
      <TodoFooter />
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
</style>
