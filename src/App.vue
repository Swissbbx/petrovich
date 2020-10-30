<template>
  <div id="app">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <Item
      v-for="product in products"
      :key="product.productId"
      :item="product"
    />
  </div>
</template>

<script>
import products from './assets/products.json'
import Item from './components/Item.vue'

export default {
  name: 'App',
  components: {
    Item,
  },
  data() {
    return {
      products: products,
    }
  },
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 30px 15px 14px 15px;
}
::selection {
  background: #b3d4fc;
  text-shadow: none;
}
</style>
