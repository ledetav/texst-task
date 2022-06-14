<template>
  <div class="all">
    <div class="header">
      <div>
        <p class="name">Добавление товара</p>
      </div>
      <div class="filter">По умолчанию</div>
    </div>
    <div class="products">
      <div class="add">
        <add-form @create="createProduct"></add-form>
      </div>
      <div>
        <cards :products="products"></cards>
      </div>
    </div>
  </div>
</template>

<script>
import AddForm from "./components/FormComponent.vue";
import Cards from "./components/CardsComponent.vue";

export default {
  name: "App",
  components: {
    AddForm,
    Cards,
  },
  data() {
    return {
      products: [
        {
          name: "Наименование товара",
          desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "../assets/card.jpg",
          price: "10 000",
        },
        {
          name: "Наименование товара",
          desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "../assets/card.jpg",
          price: "10 000",
        },
        {
          name: "Наименование товара",
          desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "../assets/card.jpg",
          price: "10 000",
        },
        {
          name: "Наименование товара",
          desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "../assets/card.jpg",
          price: "10 000",
        },
        {
          name: "Наименование товара",
          desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "../assets/card.jpg",
          price: "10 000",
        },
        {
          name: "Наименование товара",
          desc: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "../assets/card.jpg",
          price: "10 000",
        },
      ],
    };
  },
  methods: {
    createProduct(product) {
      this.products.push(product);
      localStorage.setItem('products', JSON.stringify(this.products));
    },
  },
  mounted(){
    const data = localStorage.getItem('products');
    data ? this.products = JSON.parse(data) : null;
  }
};
</script>

<style lang="scss">
@import "components/scss/app.scss";
</style>
