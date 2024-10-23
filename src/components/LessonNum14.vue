<script setup>
import { ref } from 'vue';
import ChildComponent from './ChildComponent.vue';

const msg = ref('From my father.');
</script>

<template>
  <ChildComponent>Message: {{ msg }}</ChildComponent>
</template>
