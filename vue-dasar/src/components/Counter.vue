<script setup>
import { ref } from "vue";

// let count = 0;

const props = defineProps(["name", "initialCount"]);

const counter = ref({
  count: Number(props.initialCount) || 0,
  name: "Thoriq",
});

function increment() {
  counter.value.count++;

  // State pakai DOM manipulation
  // document.getElementById("count").innerText = `Counter: ${count}`;
}
</script>

<template>
  <div>
    <h1 id="count">{{ props.name }}'s counter: {{ counter.count }}</h1>
    <button v-on:click="increment">Increment</button>
  </div>
</template>

<style scoped></style>
