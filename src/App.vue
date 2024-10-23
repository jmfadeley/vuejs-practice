<script setup>
import {ref} from 'vue';
import Lessons1Thru6 from './components/Lessons1Thru6.vue';
import LessonNum7 from './components/LessonNum7.vue';
import LessonNum8 from './components/LessonNum8.vue';
import LessonNum9 from './components/LessonNum9.vue';
import LessonNum10 from './components/LessonNum10.vue';
import LessonNum11 from './components/LessonNum11.vue';
import LessonNum12 from './components/LessonNum12.vue';
import LessonNum13 from './components/LessonNum13.vue';
import LessonNum14 from './components/LessonNum14.vue';
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
    <button @click="changeState(4)">Lesson 10</button>
    <button @click="changeState(5)">Lesson 11</button>
    <button @click="changeState(6)">Lesson 12</button>
    <button @click="changeState(7)">Lesson 13</button>
    <button @click="changeState(8)">Lesson 14</button>
  </div>
  <Lessons1Thru6 v-if="state === 0"/>
  <LessonNum7 v-else-if="state === 1"/>
  <LessonNum8 v-else-if="state === 2"/>
  <LessonNum9 v-else-if="state === 3"/>
  <LessonNum10 v-else-if="state === 4"/>
  <LessonNum11 v-else-if="state === 5"/>
  <LessonNum12 v-else-if="state === 6"/>
  <LessonNum13 v-else-if="state === 7"/>
  <LessonNum14 v-else-if="state === 8"/>
</template>

<style>
  .nav {
    display: flex;
    flex-direction: row;
    gap: 2rem;
  }

</style>