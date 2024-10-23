<script setup>
import { ref } from 'vue';
import ProdigalComponent from './ProdigalComponent.vue';

const childMsg = ref('No child msg yet CALL YOUR MOTHER');
</script>

<template>
  <ProdigalComponent @response="(msg) => childMsg = msg"/>
  <p>{{ childMsg }}</p>
</template>