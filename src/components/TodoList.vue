<template>
  <ul class="todo-list-ul">
    <li class="todo-list-li">
      <p>Add multiple li</p>
    </li>
  </ul>
</template>

<script setup></script>

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
