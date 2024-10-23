<script setup>
// eslint-disable-next-line no-unused-vars
const props = defineProps({ // compile time macro, no import req
  msg: String,
});
</script>

<template>
  <h2>{{msg || 'The perfect organism.'}}</h2>
  <slot>Fallback content.</slot>
</template>