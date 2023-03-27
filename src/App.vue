<script setup>
import { provide, ref, readonly } from "vue";
import TodoList from "./components/TodoList.vue";
import TodoForm from "./components/TodoForm.vue";

const todoList = ref(["Learn vue"]);

function updateTodoList(newList) {
  todoList.value = newList;
}

provide("todoList", {
  todoList: readonly(todoList),
  updateTodoList,
});
</script>

<template>
  <main class="main">
    <div class="wrapper-div">
      <div class="title-div">
        <h1>Todo List App</h1>

        <p v-if="todoList.length">{{ todoList.length }} TODO</p>
      </div>

      <div class="todolist-div">
        <TodoForm />
      </div>

      <div v-if="todoList.length" class="todolist-div">
        <TodoList />
      </div>

      <div v-else class="todolist-div">
        <p>No todo items to show</p>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100%;
  width: 100%;
  display: flex;
  padding: 50px;
  flex-direction: column;
}

.wrapper-div {
  width: 500px;
  padding: 20px;
  margin: 0 auto;
  border-radius: 10px;
  box-shadow: 2px 2px 10px 0 #ccc;
}

.todolist-div {
  margin-top: 20px;
}

.title-div {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
