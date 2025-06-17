<script setup>
const items = [
  {
    id: 1,
    text: "Learn vueJS",
  },
  {
    id: 2,
    text: "Learn vuex",
  },
  {
    id: 3,
    text: "Learn vue-router",
  },
];
</script>

<template>
  <h1>ToDo List App</h1>
  <ul v-for="item in items" :key="item.id">
    <li v-for="(value, index) in item" :key="index">
      {{ index }}: {{ value }}
    </li>
  </ul>

  <div v-for="n in 10">
    <p>Hello {{ n }}</p>
  </div>
</template>

<style scoped></style>
