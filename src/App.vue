<template>
  <div class="all">
    <div class="header">
      <div>
        <p class="name">Добавление товара</p>
      </div>
      <div class="filter">
        По умолчанию
      </div>
    </div>
    <div class="products">
      <div class="add">
        <add-form></add-form>
      </div> 
      <div>
        <cards></cards>
      </div>
    </div>
  </div>
</template>

<script>
import AddForm from './components/FormComponent.vue'
import Cards from './components/CardsComponent.vue'

export default {
  name: "App",
  components: {
    AddForm,
    Cards,
  }
};
</script>

<style lang="scss">
  @import "components/scss/app.scss";
</style>
