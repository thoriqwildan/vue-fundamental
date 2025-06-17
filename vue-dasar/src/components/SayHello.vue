<script setup>
import { computed, reactive, ref } from "vue";

const person = reactive({
  firstName: "Thoriq",
  lastName: "Wildan",
});

const counter = ref(0);

// Normal function
// function fullName() {
//   return `${person.firstName} ${person.lastName}`;
// }

// Computed function
const fullName = computed((oldName) => {
  console.log(`Old name: ${oldName}`);
  return `${person.firstName} ${person.lastName}`;
});

function sayHello() {
  person.firstName = document.getElementById("firstName").value;
  person.lastName = document.getElementById("lastName").value;
}

// Pakai event handling
function changeFirstName(e) {
  person.firstName = e.target.value;
}

function changeLastName(e) {
  person.lastName = e.target.value;
}
</script>

<template>
  <div>
    <button v-on:click="counter++">Counter {{ counter }}</button>
    <input
      placeholder="First Name"
      type="text"
      id="firstName"
      @input="changeFirstName"
    />
    <br />
    <input
      placeholder="Last Name"
      type="text"
      id="lastName"
      @input="changeLastName"
    />
    <br />
    <button v-on:click.prevent="sayHello">Say Hello</button>
  </div>

  <h1>Hello {{ fullName }}</h1>
</template>

<style scoped></style>
