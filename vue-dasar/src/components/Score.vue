<script setup>
import { ref } from "vue";

const score = ref(60);
</script>

<template>
  <h1>Score App</h1>
  <div v-show="score">
    <p>Score is {{ score }}</p>
  </div>
  <div v-if="score > 90">
    <p>Yay cool score {{ score }}</p>
  </div>
  <div v-else-if="score > 70">
    <p>Good score {{ score }}</p>
  </div>
  <div v-else>
    <p>Ups, bad score {{ score }}</p>
  </div>
</template>

<style scoped></style>
