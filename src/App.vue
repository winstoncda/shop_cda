<script setup lang="ts">
import TheHeader from "./components/Header.vue";
import TheFooter from "./components/Footer.vue";
import Cart from "./components/Cart/Cart.vue";
import Shop from "./components/Shop/Shop.vue";
import { reactive } from "vue";
import type { ProductInterface } from "./interfaces/Product.interface";
import data from "./data/products";

// récupération des données depuis le fichier products dans data
const products = reactive<ProductInterface[]>(data);
</script>

<template>
  <div class="app-container">
    <TheHeader class="header" />
    <!-- passage du tableau de produit -->
    <Shop :productList="products" class="shop" />
    <Cart class="cart" />
    <TheFooter class="footer" />
  </div>
</template>

<style lang="scss">
@use "./assets/base.scss" as *;
@use "./assets/debug.scss" as *;

.app-container {
  min-height: 100vh;
  display: grid;
  grid-template-areas: "header header" "shop cart" " footer footer";
  grid-template-columns: 75% 25%;
  grid-template-rows: 48px auto 48px;
}

.header {
  grid-area: header;
}

.shop {
  grid-area: shop;
}

.cart {
  grid-area: cart;
  border-left: var(--border);
  background-color: #fff;
}

.footer {
  grid-area: footer;
}
</style>
