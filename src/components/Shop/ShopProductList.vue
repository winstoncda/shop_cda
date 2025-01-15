<script setup lang="ts">
import type { ProductInterface } from "@/interfaces/Product.interface";
import ShopProduct from "./ShopProduct.vue";

defineProps<{
  productList: ProductInterface[];
}>();
</script>

<template>
  <div class="grid">
    <ShopProduct v-for="product of productList" />
  </div>
</template>

<style lang="scss" scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-auto-rows: 400px;
  gap: 20px;
}
</style>
