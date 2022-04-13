<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Tops')" href="#" class="pure-menu-link">Tops</a></li>
      <li class="pure-menu-item"><a @click="select('Dresses')" href="#" class="pure-menu-link">Dresses</a></li>
      <li class="pure-menu-item"><a @click="select('Accessories')" href="#" class="pure-menu-link">Accessories</a></li>
      <li class="pure-menu-item"><a @click="select('Bottoms')" href="#" class="pure-menu-link">Bottoms</a></li>
      <li class="pure-menu-item"><a @click="select('Shoes')" href="#" class="pure-menu-link">Shoes</a></li>
    </ul>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'BrowseView',
  components: {
    ProductList
  },
  data() {
    return {
      category: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.category === this.category);
    }
  },
  methods: {
    select(category) {
      this.category = category;
    }
  }
}
</script>
