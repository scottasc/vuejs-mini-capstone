<template>
  <div class="home">

    <h1>Products</h1>

    <div v-for="product in products">
      {{product.name}}: {{product.description}}
    </div>

</div>
</template>

<style>
</style>

<script>
var axios = require('axios');
export default {
  data: function() {
    return {
      products: []
    };
  },
  created: function() {
    axios
      .get("http://localhost:3000/api/products")
      .then(response => {
        this.products = response.data;
      });
  },
  methods: {},
  computed: {}
};
</script>