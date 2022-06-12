<template>
  <div class="form">
    <div class="input__product_name">
      <p class="form__text">Наименование товара<span>*</span></p>
      <input
        type="text"
        class="product_name"
        placeholder="Введите наименование товара"
        required
      />
    </div>
    <div class="input__product_desc">
      <p class="form__text">Описание товара</p>
      <textarea
        class="product_desc"
        placeholder="Введите описание товара"
      ></textarea>
    </div>
    <div class="input__product_img">
      <p class="form__text">Ссылка на изображение товара<span>*</span></p>
      <input
        type="url"
        class="product_img"
        placeholder="Введите наименование товара"
        required
      />
    </div>
    <div class="input__product_price">
      <p class="form__text">Цена товара<span>*</span></p>
      <input
        type="number"
        class="product_price"
        placeholder="Введите наименование товара"
        required
      />
    </div>
    <div>
      <button class="btn_add">Добавить товар</button>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
@import "scss/form.scss";
</style>