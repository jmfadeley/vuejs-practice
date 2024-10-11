<script setup>
import {ref} from 'vue';
import Lessons1Thru6 from './components/Lessons1Thru6.vue';
import Lessons7Thru11 from './components/Lessons7Thru11.vue';
  const state = ref(0);

  function changeState(newState) {
    state.value = newState;
  }
</script>

<template>
  <div class="nav">
    <button @click="changeState(0)">Lessons 1-6</button>
    <button @click="changeState(1)">Lessons 7-11</button>
    <button @click="changeState(1)">Lessons 12-15</button>
  </div>
  <Lessons1Thru6 v-if="state == 0"/>
  <Lessons7Thru11 v-else-if="state == 1"/>
  <!-- <Lessons1Thru6 v-if="state == 0"/> -->
</template>

<style>
  .nav {
    display: flex;
    flex-direction: row;
    gap: 2rem;
  }

</style>