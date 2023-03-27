<template>
  <TodoList />
</template>

<script setup>
import { provide, ref, readonly } from "vue";
import TodoList from "./components/TodoList.vue";

const todoList = ref(["Learn vue"]);

function updateTodoList(newList) {
  todoList.value = newList;
}

provide("todoList", {
  todoList: readonly(todoList),
  updateTodoList,
});
</script>

<style scoped></style>
