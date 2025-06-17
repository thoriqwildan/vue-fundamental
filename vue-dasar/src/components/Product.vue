<script setup>
import { onWatcherCleanup, ref, watch, watchEffect } from "vue";
import ProductDetail from "./ProductDetail.vue";

const productId = ref("");
const product = ref(null);

// Watch
// watch(
//   productId,
//   async (newValue, oldValue) => {
//     if (newValue) {
//       const response = await fetch(`/${newValue}.json`);
//       product.value = await response.json();
//     } else {
//       product.value = null;
//     }
//   },
//   { immediate: true }
// );

watchEffect(async () => {
  onWatcherCleanup(() => {
    console.log("Watcher cleanup");
  });

  const response = await fetch(`/${productId.value}.json`);
  product.value = await response.json();
});
</script>

<template>
  <label for="productId">
    Product ID:
    <select v-model="productId">
      <option value=""></option>
      <option value="product1">Product 1</option>
      <option value="product2">Product 2</option>
      <option value="product3">Product 3</option>
    </select>
  </label>
  <div v-if="product">
    <ProductDetail
      :id="product.id"
      :price="product.price"
      :name="product.name"
    />
  </div>
</template>

<style scoped></style>
