<template>
  <div class="card">
    <button class="delete"><p class="delete__text">X</p></button>
    <div class="card__product_img"></div>
    <div class="card__product_name">{{name}}</div>
    <div class="card__product_desc">{{description}}
    </div>
    <div class="card__product_price">{{price}}</div>
  </div>
</template>

<script>
export default {
    props: ['name', 'description', 'price']
};
</script>

<style lang="scss" scoped>
    @import "scss/card.scss";
</style>