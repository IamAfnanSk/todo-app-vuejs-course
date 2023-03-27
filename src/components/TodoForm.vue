<template>
  <form @submit.prevent="addTodo">
    <input
      type="text"
      name="todo"
      id="todo"
      v-model="todoInput"
      placeholder="Add todo"
    />
    <button type="submit">Add</button>
  </form>
</template>

<script setup>
import { inject, ref } from "vue";

const todoInput = ref("");

const { todoList, updateTodoList } = inject("todoList");

function addTodo() {
  if (todoInput.value) {
    const newTodoList = [...todoList.value, todoInput.value];
    updateTodoList(newTodoList);
    todoInput.value = "";
  }
}
</script>

<style scoped>
form {
  display: flex;
}

input {
  background: white;
  color: black;
  border: none;
  box-shadow: 0 0 0 1px #ccc;
  padding: 2px 15px;
  border-radius: 5px;
  flex-grow: 1;
}

button {
  background: black;
  color: white;
  outline: none;
  border: none;
  padding: 2px 15px;
  border-radius: 5px;
  cursor: pointer;
}
</style>
