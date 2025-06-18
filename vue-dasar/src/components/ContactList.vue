<script setup>
const [name, nameModifier] = defineModel("name", {
  type: String,
  get: (value) => {
    if (nameModifier.uppercase) {
      return value.toUpperCase();
    } else {
      return value;
    }
  },
});
const age = defineModel("age", {
  type: Number,
  default: 0,
});
const email = defineModel("email", {
  type: String,
  default: "",
});
const type = defineModel("type", {
  type: String,
});
const complain = defineModel("complain", {
  type: Boolean,
  default: false,
});
const message = defineModel("message", {
  type: String,
  default: "",
});
</script>

<template>
  <h1>Preview</h1>

  <div>
    <p>Name: {{ name }}</p>
    <p>Email: {{ email }}</p>
    <p>Age: {{ age }}</p>
    <p>Type: {{ type }}</p>
    <p>Complain: {{ complain }}</p>
    <p>Message: {{ message }}</p>
  </div>
</template>

<style scoped></style>
