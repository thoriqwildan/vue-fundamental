<script setup>
import { ref } from "vue";
import Counter from "./Counter.vue";
import CounterStateless from "./CounterStateless.vue";

const names = ["Thoriq", "Tirta"];

const counter = ref(0);

function increment(value) {
  counter.value += value;
}
</script>

<template>
  <Counter name="Thoriq" initial-count="10" />
  <Counter name="Tirta" />

  <CounterStateless
    name="Joko"
    :counter="counter"
    @click="increment"
    :increment="2"
  />
  <CounterStateless
    name="Budi"
    :counter="counter"
    @click="() => (counter -= 1)"
  />
</template>

<style scoped></style>
