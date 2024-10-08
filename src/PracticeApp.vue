<script>
import { ref } from 'vue';
  export default {
    setup() {
      const count = ref(0);
      return { 
        count
      }
  }
}
</script>

<template>
  <div id="app">
    <button @click="count++">{{count}}</button>
  </div>

</template>

<style scoped>
button {
  width: 12rem;
  height: 2rem;
  background-color: black;
  border-radius: 0.5rem;
  border-color: darkgray;
  color:gold;
  font-size: larger;
  font-weight: bolder;
  font-family: 'Courier New', Courier, monospace;
}

</style>