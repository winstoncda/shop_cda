<script setup lang="ts">
import type { ProductInterface } from "@/interfaces/Product.interface";
import ShopProductList from "./ShopProductList.vue";

// récupération des données transmises depuis App
// nous récupérons un tableau de produit. Chaque produit à les caractèristiques indiquées dans ProductInterface
defineProps<{
  productList: ProductInterface[];
}>();
</script>

<template>
  <div class="p-20">
    <ShopProductList :productList="productList" />
  </div>
</template>

<style lang="scss" scoped></style>
