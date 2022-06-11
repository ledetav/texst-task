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
        <div class="form">
          <div class="input__product_name">
            <p class="form__text">Наименование товара<span>*</span></p>
            <input type="text" class="product_name" placeholder="Введите наименование товара" required>
          </div>
          <div class="input__product_desc">
            <p class="form__text">Описание товара </p>
              <textarea class="product_desc" placeholder="Введите описание товара"></textarea>
          </div>
          <div class="input__product_img">
            <p class="form__text">Ссылка на изображение товара<span>*</span></p>
              <input type="url" class="product_img" placeholder="Введите наименование товара" required>
          </div>
          <div class="input__product_price">
            <p class="form__text">Цена товара<span>*</span></p>
              <input type="number" class="product_price" placeholder="Введите наименование товара" required>
          </div>
          <div>
            <button class="btn_add">
                Добавить товар
            </button>
          </div>
        </div>
      </div> 
      <div>
        <div class="cards">
          <div class="card">
            <div class="delete"><p class="delete__text">X</p></div>
            <div class="card__product_img"></div>
            <div class="card__product_name">Наименование товара</div>
            <div class="card__product_desc">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</div>
            <div class="card__product_price">10 000 руб.</div>
          </div>
          <div class="card">
            <div class="delete"><p class="delete__text">X</p></div>
            <div class="card__product_img"></div>
            <div class="card__product_name">Наименование товара</div>
            <div class="card__product_desc">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</div>
            <div class="card__product_price">10 000 руб.</div>
          </div>
          <div class="card">
            <div class="delete"><p class="delete__text">X</p></div>
            <div class="card__product_img"></div>
            <div class="card__product_name">Наименование товара</div>
            <div class="card__product_desc">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</div>
            <div class="card__product_price">10 000 руб.</div>
          </div>
          <div class="card">
            <div class="delete"><p class="delete__text">X</p></div>
            <div class="card__product_img"></div>
            <div class="card__product_name">Наименование товара</div>
            <div class="card__product_desc">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</div>
            <div class="card__product_price">10 000 руб.</div>
          </div>
          <div class="card">
            <div class="delete"><p class="delete__text">X</p></div>
            <div class="card__product_img"></div>
            <div class="card__product_name">Наименование товара</div>
            <div class="card__product_desc">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</div>
            <div class="card__product_price">10 000 руб.</div>
          </div>
          <div class="card">
            <div class="delete"><p class="delete__text">X</p></div>
            <div class="card__product_img"></div>
            <div class="card__product_name">Наименование товара</div>
            <div class="card__product_desc">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</div>
            <div class="card__product_price">10 000 руб.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  //components: {
  //HelloWorld
  //}
};
</script>

<style lang="scss">
  @import url("https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@0,200;0,300;0,400;0,600;0,700;0,900;1,200;1,300;1,400;1,600;1,700;1,900&display=swap");
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');

  $window_bg: #faf9f7;
  $form_bg: #FFFEFB;;
  $btn_add__bg: #EEEEEE;
  $main_text__color: #3f3f3f;
  $btn_add__text__color: #B4B4B4;

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body {
    margin: 32px;
    background: $window_bg;
  }
  .products {
    display: flex;
  }
  .name, 
  .form {
    left: 32px;
  }
  .name {
    width: 247px;
    height: 35px;
    top: 32px;

    font-family: "Source Sans Pro", sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 35px;

    color: $main_text__color;
  }
  .form {
    width: 332px;
    height: 440px;
    margin-top: 16px;
    padding: 24px;

    background: $form_bg;
    box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
    border-radius: 4px;

    .input__product_name, 
    .input__product_desc,
    .input__product_img,
    .input__product_price {
      margin: 0 0 16px 0;
      width: 284px;
    }

    .product_name,
    .product_desc,
    .product_img,
    .product_price {
      width: 100%;
      border: none;
      background: $form_bg;
      box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
      border-radius: 4px;

      padding-left: 16px;

      &::placeholder {
        font-family: 'Source Sans Pro';
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 15px;

        color: #B4B4B4;
      }
    }
    .product_name,
    .product_img,
    .product_price {
      height: 36px;
    }

    .input__product_name {
      height: 53px;
    }
    
    .input__product_desc {
      height: 125px;
      .product_desc {
        height: 108px;
        padding-top: 10px;
        resize: none;
      }
    }

    .form__text {
        margin-bottom: 4px;
        font-family: 'Source Sans Pro';
        font-style: normal;
        font-weight: 400;
        font-size: 12px;
        line-height: 13px;

        letter-spacing: -0.02em;

        color: #49485E;
        span {
          color: #FF8484;
          font-weight: 600;
        }
      }
    .btn_add {
      width: 284px;
      height: 36px;
      margin-top: 8px;

      background: $btn_add__bg;
      border-radius: 10px;
      font-family: 'Inter';
      font-style: normal;
      font-weight: 600;
      font-size: 14px;
      line-height: 15px;

      text-align: center;
      letter-spacing: -0.02em;

      color: $btn_add__text__color;
  }
  }

  .cards {
    margin-left: 16px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: flex-start;
    justify-content: space-around;
    align-content: space-between;
    .card {
      position: relative;
      width: 332px;
      height: 423px;
      margin-top: 16px;

      background: #FFFEFB;
      box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
      border-radius: 4px;
      .card__product_img {
        height: 200px;
        background: url(@/assets/card.png);
        background-size: contain;
        border-radius: 4px 4px 0px 0px;
      }
      .card__product_name {
        margin: 16px;
        font-family: 'Source Sans Pro';
        font-style: normal;
        font-weight: 600;
        font-size: 20px;
        line-height: 25px;

        color: #3F3F3F;
      }
      .card__product_desc {
        width: 300px;
        margin: 0 0 32px 16px;

        font-family: 'Source Sans Pro';
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 20px;

        color: #3F3F3F;
      }

      .card__product_price {
        margin: 0 0 24px 16px;
        font-family: 'Source Sans Pro';
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 30px;

        color: #3F3F3F;
      }
    }
  }
  .filter {
    position: absolute;
    width: 121.49px;
    height: 36px;
    top: 31px;
    left: calc(87% + 30px);
    padding: 10px 0 11px 16px;

    background: #FFFEFB;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    border-radius: 4px;

    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 15px;

    color: #B4B4B4;
  }

  .delete {
    position: absolute;
    width: 32px;
    height: 32px; 
    background: #FF8484;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: 10px;

    left: calc(90% + 8px);
    top: -8px;

    .delete__text {
      position: absolute;
      left: 9px;
      top: 5px;

      font-size: 20px;

      color: #FFFEFB;
    }
  }
</style>
