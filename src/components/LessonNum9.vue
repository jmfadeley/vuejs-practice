<script setup>
  import { ref, onMounted } from 'vue';

  const pElementRef = ref(null); // Allows for manual DOM manipulation.
  // Null for now because it does not exist on setup. AFTER mounting, things change.

  onMounted(()=> { // Lifecycle hook magic.
    pElementRef.value.textContent = "TURN DOWN FOR WHAT?!";
  })
</script>

<template>
  <p class="lesson9__ref" ref="pElementRef">Hello sailor.</p>
</template>

<style>
  .lesson9__ref {
    color: red;
  }
</style>