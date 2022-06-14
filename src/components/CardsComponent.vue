<template>
  <div class="cards">
    <product-card
      v-for="product in products"
      :key="product.index"
      :name="product.name"
      :description="product.desc"
      :img="product.img"
      :price="product.price"
    ></product-card>
  </div>
</template>

<script>
import ProductCard from "./CardComponent.vue";

export default {
  components: {
    ProductCard,
  },
  props: ['products'],
};
</script>

<style lang="sass" scoped>
.cards
  margin-left: 16px
  display: flex
  flex-direction: row
  flex-wrap: wrap
  align-content: flex-start
  justify-content: space-around
  align-content: space-between
</style>