<template>
  <div class="card">
    <button class="delete"><p class="delete__text">X</p></button>
    <div class="card__info">
      <img :src="img" class="card__product_img" />
      <div class="card__product_name">{{ name }}</div>
      <div class="card__product_desc">{{ description }}</div>
      <div class="card__product_price">{{ price }} руб.</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["name", "description", "img", "price"],
};
</script>

<style lang="scss" scoped>
@import "scss/card.scss";
</style>