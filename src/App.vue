<template>
  <v-app id="inspire">
    <v-app-bar app class="secondary">
      <v-toolbar-title class="nav-bar--title">STRAPI APP</v-toolbar-title>
    </v-app-bar>

    <v-main class="blue lighten-2">
      <ProductList :products="products" />
    </v-main>
    <v-footer></v-footer>
  </v-app>
</template>

<script>
import ProductList from "@/components/ProductList";
import products from "../mocks/products.json";

export default {
  name: 'App',
  components: {
    ProductList,
  },
  created() {
    this.products = products;
  },
  data: () => ({
    products: [],
  }),
};
</script>

<style scoped>
  .nav-bar--title {
    color: white;
  }
</style>
