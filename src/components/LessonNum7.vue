<script setup>
import { ref } from 'vue';

let id = 0;

const newTodo = ref('');
const todos = ref([
  { id: id++, text: 'Learn HTML'},
  { id: id++, text: 'Learn JavaScript'},
  { id: id++, text: 'Learn Vue'},
]);

function addTodo() {
  todos.value.push({id: id++, text: newTodo.value }); // Mutating.
  newTodo.value = '';
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" required placeholder="new todo foo!">
    <button>Add todo</button>
  </form>

  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{todo.text}}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>

<style>
  ul {
    display: flex;
    flex-direction: column;
    padding-left: 0;
  }

  form, li {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
</style>