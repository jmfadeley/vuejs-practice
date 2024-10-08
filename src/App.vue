
<script setup>
import { reactive, ref } from 'vue';

  // Component logic.
  // Declare some reactive state here.

  // Reactive works on objects and arrays. Ref takes in anything
  // but exposes it through `.value`
  const counter = reactive({
    count: 0
  });

  const message = ref('Hello world!');
  console.log(message.value);

  const behold = ref ('Watch me now, AH!');

  counter.count++;

  // v-bind is a directive used to attribute to a dynamic value. 
  // It alwayts starts with v-, but you can just use a colon with
  // the attribute in question. This makes the attributes responsive 
  // to JS changes.

  const titleId = ref('title');
  // const accentClass = ref('accent'); // The magic!

  const count = ref(0);
  function increment() {
    // Update component state:
    count.value++;
  }
</script>

<template>
  <h1 v-bind:id="titleId">{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p>
  <p>{{ behold.split('').reverse().join('') }}</p>

  <button v-on:click="increment"> Count is: {{ count }}</button>
  <button @click="increment"> Second count is: {{ count }}</button>

  <!-- <h2 :class="accentClass">Make me red!</h2> -->
</template>

<style>
  .accent {
    color: red;
  }

  button {
    display: block;
    margin: 1rem 0;
    padding: 0.5rem;
    background-color: chocolate;
    border-radius:1rem;
    border-color: azure;
    font-weight: bold;
    font-size: 1rem;
    color:white;
  }
</style>