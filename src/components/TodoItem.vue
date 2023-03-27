<template>
  <p class="todo-item">
    <span class="todo-text">{{ todo }}</span>
    <TodoDelete @delete="deleteTodo" :id="id" />
  </p>
</template>

<script setup>
import { inject, toRefs, ref } from "vue";
import TodoDelete from "./TodoDelete.vue";

const props = defineProps({
  todo: {
    type: String,
    required: true,
  },
  id: {
    type: Number,
    required: true,
  },
});

const { todo, id } = toRefs(props);

const { todoList, updateTodoList } = inject("todoList");

function deleteTodo(id) {
  const newList = [...todoList.value];
  newList.splice(id, 1);
  updateTodoList(newList);
}
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 10px;
}

.todo-text {
  font-weight: 500;
}
</style>
