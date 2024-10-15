<script setup>
  import { ref, onMounted } from 'vue';

  const pElementRef = ref(null); // Allows for manual DOM manipulation.
  // Null for now because it does not exist on setup. AFTER mounting, things change.

  onMounted(()=> { // Lifecycle hook magic.
    pElementRef.value.textContent = "TURN DOWN FOR WHAT?!";
  })
</script>

<template>
  <p ref="pElementRef">Hello sailor.</p>
</template>

<style>
  p {
    color: red;
  }
</style>