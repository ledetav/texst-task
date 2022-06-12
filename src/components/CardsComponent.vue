<template>
  <div class="cards">
    <product-card
      v-for="n in 6"
      :key="n"
      :name="product.name"
      :description="product.desc"
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
  data() {
    return {
      product: {
        name: "Наименование товара",
        desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
        price: "10 000 руб.",
      },
    };
  },
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