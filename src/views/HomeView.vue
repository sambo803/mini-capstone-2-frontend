<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!!!",
      products: [],
    };
  },
  created: function () {
    this.indexProducts();
  },
  methods: {
    indexProducts: function () {
      axios.get("/products.json").then((response) => {
        console.log("products index", response);
        this.products = response.data;
      });
    },
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
   <div v-for="product in products" v-bind:key="product.id">
   <h2>{{product.name}}</h2>
   <h3>{{product.description}}</h3>
   <h3>{{product.price}}</h3>
   </div>
   
   
 
  </div>
</template>

<style></style>
