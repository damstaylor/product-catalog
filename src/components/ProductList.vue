<template>
  <v-row justify="center">
    <v-card class="ma-2" v-for="(product, index) in products" :key="index" max-width="270">
      <v-card-title>{{ product.name }}</v-card-title>
      <v-card-text>
        <strong>
          {{ getPrice(product) }}
        </strong>
      </v-card-text>
    </v-card>
  </v-row>
</template>

<script>
import {defineComponent} from "vue"

export default defineComponent({
  name: "ProductList",
  props: {
    products: { type: Array, default: () => [] },
  },
  data: () => ({
    apiUrl: "",
  }),
  computed: {
    getPrice() {
      return product => product.unit_price ? `${product.unit_price},00€` : "";
    },
  },
})
</script>
