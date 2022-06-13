<template>
  <div class="form">
    <div class="input__product_name">
      <p class="form__text">Наименование товара<span>*</span></p>
      <input
        type="text"
        class="product_name"
        placeholder="Введите наименование товара"
        v-model="name"
        @blur="v$.name.$touch()"
        :class="{
          error_input: v$.name.$error === true,
          norm_input: v$.name.$error === false,
        }"
      />
      <span class="error" v-if="v$.name.$error">
        <template v-if="v$.name.required.$invalid">
          Поле является обязательным.
        </template>
      </span>
    </div>
    <div class="input__product_desc">
      <p class="form__text">Описание товара</p>
      <textarea
        class="product_desc norm_input"
        placeholder="Введите описание товара"
      ></textarea>
    </div>
    <div class="input__product_img">
      <p class="form__text">Ссылка на изображение товара<span>*</span></p>
      <input
        type="url"
        class="product_img"
        placeholder="Введите ссылку"
        v-model="img"
        @blur="v$.img.$touch()"
        :class="{
          error_input: v$.img.$error === true,
          norm_input: v$.img.$error === false,
        }"
      />
      <span class="error" v-if="v$.img.$error">
        <template v-if="v$.img.url.$invalid"> Вы не ввели ссылку. </template>
        <template v-else> Поле является обязательным. </template>
      </span>
    </div>
    <div class="input__product_price">
      <p class="form__text">Цена товара<span>*</span></p>
      <input
        type="text"
        class="product_price"
        placeholder="Введите цену"
        v-model="price"
        @blur="v$.price.$touch() & addMask()"
        :class="{
          error_input: v$.price.$error === true,
          norm_input: v$.price.$error === false,
        }"
      />
      <span class="error" v-if="v$.price.$error">
        <template v-if="v$.price.required.$invalid">
          Поле является обязательным.
        </template>
      </span>
    </div>
    <div>
      <button
        class="btn_add"
        :disabled="
          v$.name.$error === true ||
          v$.img.$error === true ||
          v$.price.$error === true ||
          name == null ||
          img == null ||
          price == null
        "
        :class="[
          {
            disabled_btn:
              v$.name.$error === true ||
              v$.img.$error === true ||
              v$.price.$error === true ||
              name == null ||
              img == null ||
              price == null,
          },
          {
            normal_btn:
              v$.name.$error === false &&
              v$.img.$error === false &&
              v$.price.$error === false &&
              name != null &&
              img != null &&
              price != null,
          },
        ]"
      >
        Добавить товар
      </button>
    </div>
  </div>
</template>
<script>
import useValidate from "@vuelidate/core";
import { required, url } from "@vuelidate/validators";
export default {
  data() {
    return {
      v$: useValidate(),
      name: null,
      img: null,
      price: null,
    };
  },
  validations() {
    return {
      name: { required },
      img: { required, url },
      price: { required },
    };
  },
  methods: {
    addMask() {
      var price = this.price;
      function mask(price) {
        return price.replace(/\B(?=(\d{3})+(?!\d))/g, " ");
      }
      this.price = mask(price);
    },
  },
};
</script>
<style lang="scss" scoped>
@import "scss/form.scss";
</style>