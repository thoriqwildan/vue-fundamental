<script setup lang="ts">
console.info("Hello vue component loaded");

const hello = "<h1>Hello Thoriq</h1>";
const classHello = "hello"; // Template attribute binding
const buttonDisabled = false; // Boolean attribute binding

// Multiple attribute binding
const data = {
  id: "hello",
  class: "hello",
};
</script>

<template>
  <h1 :class="classHello">{{ hello }}</h1>
  <div :class="classHello" v-html="hello"></div>

  <h1 v-bind="data">Ini multiple Attribute</h1>

  <button :disabled="buttonDisabled">Play The Game!</button>
</template>

<style scoped>
.hello {
  color: green;
}
</style>
