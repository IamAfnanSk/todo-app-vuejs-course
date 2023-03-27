<template>
  <ul class="todo-list-ul">
    <li class="todo-list-li" v-for="(todo, index) in todoList">
      <TodoItem :todo="todo" :id="index" />
    </li>
  </ul>
</template>

<script setup>
import { inject } from "vue";
import TodoItem from "./TodoItem.vue";

const { todoList } = inject("todoList");
</script>

<style scoped>
.todo-list-ul,
.todo-list-li {
  list-style: none;
  margin: 0;
  padding: 0;
}

.todo-list-ul {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.todo-list-li {
  padding: 10px;
  border-radius: 5px;
  box-shadow: 0 0 5px #ccc;
  width: 100%;
}
</style>
