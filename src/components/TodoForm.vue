<template>
  <form>
    <input type="text" name="todo" id="todo" placeholder="Add todo" />
    <button type="submit">Add</button>
  </form>
</template>

<script setup></script>

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
