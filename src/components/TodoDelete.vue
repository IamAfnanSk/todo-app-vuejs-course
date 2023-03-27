<template>
  <button @click="$emit('delete', id)">X</button>
</template>

<script setup>
import { toRefs } from "vue";

const props = defineProps({
  id: {
    type: Number,
    required: true,
  },
});
const emit = defineEmits(["delete"]);

const { id } = toRefs(props);
</script>

<style scoped>
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
