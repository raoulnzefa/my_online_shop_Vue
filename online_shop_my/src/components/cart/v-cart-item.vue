<template>
<div class="container">
  <div class='v-cart-item product__shopping'>
  <div class="product">
    <img class="v-cart-item__image" :src=" require('../../assets/images/' + cart_item_data.image) " alt="">
    <div class="v-cart-item__info product__details">
      <p>{{cart_item_data.name}}</p>
      
      <p>{{cart_item_data.article}}</p>
    </div>
  </div>
  <div class="product__wrapper">
							<div class="product__price">
              <p>{{cart_item_data.price | toFix | formattedPrice}}</p>
              </div>
    <div class="v-cart-item__quantity product__qty">
      <span class="quantity__tools">
        <span class="quantity__btn" @click="decrementItem">-</span>
        {{cart_item_data.quantity}}
        <span class="quantity__btn" @click="incrementItem">+</span>
      </span>
    </div>
    <div class="product__shipping">
    FREE
		</div>
    <div class="product__subtotal">
    $
		</div>
    <button @click="deleteFromCart" class="product__action"><i class="fas fa-times-circle"></i></button>
  </div>
  </div>
  </div>
</template>

<script>
import toFix from '../../filters/toFix'
import formattedPrice from "../../filters/price-format";


  export default {
    name: "v-cart-item",
    props: {
      cart_item_data: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    data() {
      return {}
    },
    filters: {
      toFix,
      formattedPrice
    },
    computed: {},
    methods: {
      decrementItem() {
        this.$emit('decrement')
      },
      incrementItem() {
        this.$emit('increment')
      },
      deleteFromCart() {
        this.$emit('deleteFromCart')
      }
    }
  }
</script>

<style lang="scss">
  .v-cart-item {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
    padding: $padding*2;
    margin-bottom: $margin*2;

    .quantity__btn {
      cursor: pointer;
    }

    .quantity__tools {
      user-select: none;
    }
  }
  .product__shopping {
    display: flex;
    justify-content: space-between;
    padding-bottom: 25px;
    border-bottom: 1px solid #eaeaea;
    margin-top: 20px;
    color: #656565;
}

.product__shopping > div:first-child {
    width: 460px;
}

.product__shopping > div:not(:first-child) {
    display: flex;
    justify-content: center;
    align-items: center;
}

.product__price {
    width: 78px;
    margin-left: 50px;
}

.product__qty {
    width: 68px;
    font-size: 16px;
    margin-left: 98px;
}

.product__qty input {
    width: 54px;
    border: 1px solid #eaeaea;
    text-align: center;
    height: 30px;
    color: #656565;
}

.product__shipping {
    width: 62px;
    margin-left: 75px;
}

.product__subtotal {
    width: 66px;
    margin-left: 79px;
}

.product__action {
    width: 50px;
    margin-left: 54px;
    cursor: pointer;
    border: none;
    outline: none;
    background: none;
}

.product__shopping .product {
    display: flex;
}

.product__shopping .product img {
    margin-right: 20px;
}

.v-cart-item__image {
    height: 115px;
}

.product__details {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding-top: 13px;
    padding-bottom: 22px;
}

.product__size,
.product__color {
    font-weight: 300;
}

.product__name {
    font-size: inherit;
    font-weight: inherit;
    text-transform: uppercase;
    margin-top: -4px;
    letter-spacing: -0.03em;
    margin-bottom: 28px;
}

.product__param {
    font-weight: 400;
}

</style>
