<script setup>
import MyButton from "./MyButton.vue";

function clickHandler() {
  alert("Button clicked!");
}
</script>

<template>
  <MyButton class="button" @click="clickHandler" name="Thoriq" />
</template>

<style scoped>
.button {
  background-color: blue;
  color: white;
  border: none;
}
</style>
