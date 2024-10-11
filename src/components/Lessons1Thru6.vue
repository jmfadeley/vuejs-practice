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

  const text = ref('');
  const words = ref('');

  function onInput(e) {
    text.value = e.target.value;
  }

  // By using both the bind and on, two way bindings are possible.
  // But model just combines both.

  const flip = ref(true);

  function toggle() {
    flip.value = !flip.value;
  }
</script>

<template>
  <h1 v-bind:id="titleId">{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p>
  <p>{{ behold.split('').reverse().join('') }}</p>

  <div>
    <button v-on:click="increment"> Count is: {{ count }}</button>
    <button @click="increment"> Second count is: {{ count }}</button>
  </div>
  <div>
    Look at this iffery.
    <p v-if="count % 2 == 0 && count < 10">Is even.</p>
    <p v-else-if="count % 3 == 0 && count < 10">Is odd & multiple of 3.</p>
    <p v-else-if="count % 2 != 0 && count < 10">Is odd.</p>
    <p v-else>Just stop. I'm tired.</p>
  </div>
  <!-- <h2 :class="accentClass">Make me red!</h2> -->

  <div>
    <input :class="textfield" 
      :value="text" 
      @input="onInput" 
      placeholder="ENTER THE WORDS">
    <p>{{ text }}</p>
    <input v-model="words" placeholder="Work harder not smarter.">
    <p>{{ words }}</p>
    <button @click="toggle">FLIP!</button>
    <h1 v-if="flip">I can see!</h1>
    <h1 v-else>I am blind!</h1>
  </div>
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
  
  .textfield {
    display: block;
  }
</style>