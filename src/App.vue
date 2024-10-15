<script setup>
import {ref} from 'vue';
import Lessons1Thru6 from './components/Lessons1Thru6.vue';
import LessonNum7 from './components/LessonNum7.vue';
import LessonNum8 from './components/LessonNum8.vue';
import LessonNum9 from './components/LessonNum9.vue';
  const state = ref(0);

  function changeState(newState) {
    state.value = newState;
  }
</script>

<template>
  <div class="nav">
    <button @click="changeState(0)">Lessons 1-6</button>
    <button @click="changeState(1)">Lesson 7</button>
    <button @click="changeState(2)">Lesson 8</button>
    <button @click="changeState(3)">Lesson 9</button>
  </div>
  <Lessons1Thru6 v-if="state == 0"/>
  <LessonNum7 v-else-if="state == 1"/>
  <LessonNum8 v-else-if="state == 2"/>
  <LessonNum9 v-else-if="state == 3"/>
</template>

<style>
  .nav {
    display: flex;
    flex-direction: row;
    gap: 2rem;
  }

</style>