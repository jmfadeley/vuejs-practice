<script setup>
import ChildComponent from './ChildComponent.vue';
import { ref } from 'vue';

const greeting = ref('Go already son!');
</script>

<template>
  <ChildComponent :msg="greeting"/>
</template>