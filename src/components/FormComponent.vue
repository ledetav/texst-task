<template>
  <div class="form">
    <div class="input__product_name">
      <p class="form__text">Наименование товара<span>*</span></p>
      <input
        type="text"
        class="product_name"
        placeholder="Введите наименование товара"
        v-model="product.name"
        @blur="v$.product.name.$touch()"
        :class="{
          error_input: v$.product.name.$error === true,
          norm_input: v$.product.name.$error === false,
        }"
      />
      <span class="error" v-if="v$.product.name.$error">
        <template v-if="v$.product.name.required.$invalid">
          Поле является обязательным.
        </template>
      </span>
    </div>
    <div class="input__product_desc">
      <p class="form__text">Описание товара</p>
      <textarea
        v-model="product.desc"
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
        v-model="product.img"
        @blur="v$.product.img.$touch()"
        :class="{
          error_input: v$.product.img.$error === true,
          norm_input: v$.product.img.$error === false,
        }"
      />
      <span class="error" v-if="v$.product.img.$error">
        <template v-if="v$.product.img.url.$invalid">
          Вы не ввели ссылку.
        </template>
        <template v-else> Поле является обязательным. </template>
      </span>
    </div>
    <div class="input__product_price">
      <p class="form__text">Цена товара<span>*</span></p>
      <input
        type="text"
        class="product_price"
        placeholder="Введите цену"
        v-model="product.price"
        @blur="v$.product.price.$touch() & addMask()"
        :class="{
          error_input: v$.product.price.$error === true,
          norm_input: v$.product.price.$error === false,
        }"
      />
      <span class="error" v-if="v$.product.price.$error">
        <template v-if="v$.product.price.required.$invalid">
          Поле является обязательным.
        </template>
      </span>
    </div>
    <div>
      <button
        class="btn_add"
        @click="createProduct"
        @submit.prevent
        :disabled="
          v$.product.name.$error === true ||
          v$.product.img.$error === true ||
          v$.product.price.$error === true ||
          product.name == null ||
          product.img == null ||
          product.price == null
        "
        :class="[
          {
            disabled_btn:
              v$.product.name.$error === true ||
              v$.product.img.$error === true ||
              v$.product.price.$error === true ||
              product.name == null ||
              product.img == null ||
              product.price == null,
          },
          {
            normal_btn:
              v$.product.name.$error === false &&
              v$.product.img.$error === false &&
              v$.product.price.$error === false &&
              product.name != null &&
              product.img != null &&
              product.price != null,
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
      product: {
        name: null,
        desc: null,
        img: null,
        price: null,
      },
    };
  },
  validations() {
    return {
      product: {
        name: { required },
        img: { required, url },
        price: { required },
      },
    };
  },
  methods: {
    addMask() {
      var price = this.product.price;
      function mask(price) {
        return price.replace(/\B(?=(\d{3})+(?!\d))/g, " ");
      }
      this.product.price = mask(price);
    },
    createProduct() {
      this.$emit('create', this.product);
      this.product = {
        name: '',
        desc: '',
        img: '',
        price: '',
      };
    },
  },
};
</script>
<style lang="scss" scoped>
@import "scss/form.scss";
</style>