<template>
  <div class='v-catalog-item'>

    <v-popup
        v-if="isInfoPopupVisible"
        rightBtnTitle="Add to cart"
        :popupTitle="product_data.name"
        @closePopup="closeInfoPopup"
        @rightBtnAction="addToCart"
    >
      <img class="v-catalog-item__image" :src=" require('../../assets/images/' + product_data.image) " alt="img">
      <div>
        <p class="v-catalog-item__name">{{product_data.name}}</p>
        <p class="v-catalog-item__price">Price: {{product_data.price | toFix | formattedPrice}}.</p>
        <p class="v-catalog-item__price">{{product_data.category}}</p>
      </div>
    </v-popup>

    <div class="featuredItem">
    <div class="featuredImgWrap">
    
    <div class="featuredBuy">
    <button
        class="v-catalog-item__show-info"
        @click="showPopupInfo"
    >
      Show info
    </button>
    <br>
    <button
        class="v-catalog-item__add_to_cart_btn btn"
        @click="addToCart"
        
    > <img src="../../assets/forma.png" alt="forma">
    Add to cart
    </button>
</div>
<img class="v-catalog-item__image" :src=" require('../../assets/images/' + product_data.image) " alt="img" @click="productClick">
</div>
  <div class="featuredNameAndPrice">
    <p class="v-catalog-item__name featuredItemName">{{product_data.name}}</p>
    <p class="v-catalog-item__price featuredItemPrice">Price: {{product_data.price | toFix | formattedPrice}}</p>
  </div>
  </div>
  </div>
</template>

<script>
  import vPopup from '../popup/v-popup'
  import toFix from '../../filters/toFix'
  import formattedPrice from "../../filters/price-format";

  export default {
    name: "v-catalog-item",
    components: {
      vPopup
    },
    props: {
      product_data: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    data() {
      return {
        isInfoPopupVisible: false
      }
    },
    filters: {
      toFix,
      formattedPrice
    },
    computed: {},
    methods: {
      productClick() {
        this.$emit('productClick', this.product_data.article)
      },
      showPopupInfo() {
        this.isInfoPopupVisible = true;
      },
      closeInfoPopup() {
        this.isInfoPopupVisible = false;
      },
      addToCart() {
        this.$emit('addToCart', this.product_data);
      }
    },
    mounted() {
      this.$set(this.product_data, 'quantity', 1)
    }
  }
</script>

<style lang="scss">
 .v-catalog-item__show-info {
   margin-right: 10px;
   border-radius: 5px;
   outline: none;
 }
 .popup_wrapper {
   background: rgba(64, 64, 64, 0.6) !important;
       position: fixed;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: 1000;
 }
</style>
