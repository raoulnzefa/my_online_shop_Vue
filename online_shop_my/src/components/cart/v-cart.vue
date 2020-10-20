<template>
  <div class='v-cart'>
    <router-link :to="{name: 'catalog'}">
      <div class="v-catalog__link_to_cart">Back to Catalog</div>
    </router-link>
    <h1>Cart</h1>
    <section class="arrivals" id="arrivals">
        <div class="container arrivalsWrap">
            <h2 class="arrivals__title">New Arrivals</h2>
               <nav class="arrivals__navigation">
                  <a href="#">Home</a>
                  <span>/</span>
                  <a href="#">Men</a>      
                  <span>/</span>      
                  <a href="#">New arrivals</a>      
                </nav>                                  
        </div>
    </section>
    <section class="products" id="products">
		<div class="container">
			<div class="productsCart">
					<h2 class="products__title">Product details</h2>
					<ul class="products__navigation">
						<li class="products__link">
							Unite price
						</li>
						<li class="products__link">
							Quantity
						</li>
						<li class="products__link">
							Shipping
						</li>
						<li class="products__link">
							Subtotal
						</li>
						<li class="products__link">
							Action
						</li>
					</ul>
			</div>
		</div>
	</section>
    <p v-if="!cart_data.length">There are no products in cart...</p>
    <v-cart-item
    class="v-cartWr"
        v-for="(item, index) in cart_data"
        :key="item.article"
        :cart_item_data="item"
        @deleteFromCart="deleteFromCart(index)"
        @increment="increment(index)"
        @decrement="decrement(index)"
    />
    <section class="btns" id="btns">
		<div class="container btnsWrap">
				<button class="btns__first">Clear shopping cart</button>
				<button class="btns__second">Continue shopping</button>
		</div>
	</section>
  <section class="contacts" id="contacts">
		<div class="container">
			<div class="contactsWrap">
					<form class ="adresWrap">
						<h2>Shipping adress</h2>
						<select required>
							<option value="">Bangladesh</option>
							<option>Russia</option>
							<option>Australia</option>
						</select>
						<input required type="text" placeholder="State">
						<input required type="number" placeholder="Postcode / Zip">
						<button>Get a quote</button>
					</form>
					<form class="contacts__discont">
						<h2>Coupon discount</h2>
						<label for="state">Enter your coupon code if you have one</label>
						<input id="state" type="text" placeholder="State">
						<button>Apply coupon</button>
					</form>
					<div class="contacts__total">
						<div class="contacts__sub">
							<span>Sub total</span>
							<span>$___</span>
						</div>
						<div class="contacts__grand">
							<span class="contacts__grand_first">Grand total</span>
							<span><p>{{cartTotalCost | toFix | formattedPrice}}</p></span>
						</div>
						<button class="contacts__grandBtn">Proceed to checkout</button>
					</div>
			</div>
		</div>
	</section>
    <section class="subscribe" id="subscribe">
		<div class="container subscribeWrap">
					<div class="subscribe__bin">
						<img src="../../assets/face.png" alt="Face">
						<div class="subscribe__content">
							<p class="subscribe__text">“Vestibulum quis porttitor dui! Quisque viverra
								nunc mi,
								a
								pulvinar purus condimentum a. Aliquam condimentum mattis neque sed
								pretium”</p>
							<span>Bin Burhan</span>
							<p class="subscribe__bd">Dhaka, Bd</p>
							<div class="subscribe__reviews">
								<div></div>
								<div></div>
								<div></div>
							</div>
						</div>
					</div>
					<div class="subscribe__wrapper">
						<h4 class="subscribe__title">Subscribe</h4>
						<p class="subscribe__our">FOR OUR NEWLETTER AND PROMOTION</p>
						<form action="#" class="subscribe__form d-flex">
							<input type="email" name="email" placeholder="Enter Your Email" required>
							<button>Subscribe</button>
						</form>
					</div>
		</div>
	</section>
  <section class="company" id="company">
		<div class="container compWr">
					<div class="company__brand">
						<a href="#" class="logo logo2 d-flex">
							<img src="../../assets/logo.png" alt="Logo">
							<p>BRAN
								<span>D</span>
							</p>
						</a>
						<p class="company__text company__text_first">Objectively transition extensive
							data
							rather than
							cross functional solutions. Monotonectally syndicate multidisciplinary
							materials
							before go
							forward benefits. Intrinsicly syndicate an expanded array of processes and
							cross-unit
							partnerships.</p>
						<p class="company__text company__text_second">Efficiently plagiarize 24/365
							action items
							and
							focused infomediaries. Distinctively seize superior initiatives for wireless
							technologies.
							Dynamically optimize.</p>
					</div>
          <div class="companyWrap">
					<div class="company__column company__column_first">
						<h2>COMPANY</h2>
						<a href="#">Home</a>
						<a href="#">Shop</a>
						<a href="#">About</a>
						<a href="#">How It Works</a>
						<a href="#">Contact</a>
					</div>
					<div class="company__column company__column_second">
						<h2>INFORMATION</h2>
						<a href="">Tearms & Condition</a>
						<a href="">Privacy Policy</a>
						<a href="">How to Buy</a>
						<a href="">How to Sell</a>
						<a href="">Promotion</a>
					</div>
					<div class="company__column company__column_third">
						<h2>SHOP CATEGORY</h2>
						<a href="">Men</a>
						<a href="">Women</a>
						<a href="">Child</a>
						<a href="">Apparel</a>
						<a href="">Browse All</a>
					</div>
          </div>
		</div>
	</section>
  <footer class="footer" id="footer">
		<div class="container footerWrap">
					<div class="copyrights__first">
						&copy; 2017 Brand All Rights Reserved.
					</div>
					<div class="copyrights__second">
						<a href=""><i class="fab fa-facebook-f"></i></a>
						<a href=""><i class="fab fa-twitter"></i></a>
						<a href=""><i class="fab fa-linkedin-in"></i></a>
						<a href=""><i class="fab fa-pinterest-p"></i></a>
						<a href=""><i class="fab fa-google-plus-g"></i></a>
					</div>
		</div>
	</footer>
  </div>
</template>

<script>
  import vCartItem from './v-cart-item'
  import toFix from "../../filters/toFix";
  import formattedPrice from "../../filters/price-format";
  import {mapActions} from 'vuex'

  export default {
    name: "v-cart",
    components: {
      vCartItem
    },
    props: {
      cart_data: {
        type: Array,
        default() {
          return []
        }
      }
    },
    data() {
      return {}
    },
    filters: {
      formattedPrice,
      toFix
    },
    computed: {
      cartTotalCost() {
        let result = []

        if (this.cart_data.length) {
          for (let item of this.cart_data) {
            result.push(item.price * item.quantity)
          }

          result = result.reduce(function (sum, el) {
            return sum + el;
          })
          return result;
        } else {
          return 0
        }
      }
    },
    methods: {
      ...mapActions([
        'DELETE_FROM_CART',
        'INCREMENT_CART_ITEM',
        'DECREMENT_CART_ITEM'
      ]),
      increment(index) {
        this.INCREMENT_CART_ITEM(index)
      },
      decrement(index) {
        this.DECREMENT_CART_ITEM(index)
      },
      deleteFromCart(index) {
        this.DELETE_FROM_CART(index)
      }
    }
  }
</script>

<style lang="scss">
  .v-cart {
    margin-bottom: 100px;
    &__total {
      position: fixed;
      bottom: 0;
      right: 0;
      left: 0;
      padding: $padding*2 $padding*3;
      display: flex;
      justify-content: center;
      background: $green-bg;
      color: #ffffff;
      font-size: 20px;
    }

    .total__name {
      margin-right: $margin*2;
    }
  }
  .v-cartWr {
    width: 1140px;
    margin: 0 auto;
  }
  .v-catalog__link_to_cart {
    background: #ef5b70;
    color: #fff;
  }
  /* ------ Btns ------ */

.btns {
    padding-top: 30px;
    padding-bottom: 48px;
}

.btns button {
    padding: 20px 40px;
    border: 1px solid #eaeaea;
    background-color: #ffffff;
    color: #4a4a4a;
    text-transform: uppercase;
    font-weight: 700;
}

.btns button:hover {
    background: #d26070;
    color: #fff;
}

.btns button:active {
    background: #fff;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}
.btns button:focus {
    box-shadow: none;
}

.btns__second {
    margin-left: 232px;
}
.btns__first {
    float: left;
}
.btnsWrap {
  justify-content: space-between;
}
/* ------ Contacts ------ */

.contacts h2 {
    margin-top: 0;
    margin-bottom: 17px;
    text-transform: uppercase;
    font-size: 16px;
}

.contacts select,
.contacts input {
    height: 45px;
    border: 1px solid #eaeaea;
    background-color: #ffffff;
    width: 100%;
    color: #b1b1b1;
    font-size: 13px;
    font-weight: 300;
    padding: 13px;
    font-family: inherit;
    outline: none;
    box-sizing: border-box;
    margin-bottom: 20px;
}

.contacts select:focus {
    outline: none;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}

.contacts input:focus {
    outline: none;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}

.contacts input::-webkit-input-placeholder {
    /* Chrome/Opera/Safari */
    color: #b1b1b1;
}

.contacts input::-moz-placeholder {
    /* Firefox 19+ */
    color: #b1b1b1;
}

.contacts input:-ms-input-placeholder {
    /* IE 10+ */
    color: #b1b1b1;
}

.contacts input:-moz-placeholder {
    /* Firefox 18- */
    color: #b1b1b1;
}

.contacts button {
    padding: 12px 15px;
    border: 1px solid #eaeaea;
    background: white;
    font-family: inherit;
    text-transform: uppercase;
    color: #4a4a4a;
    font-weight: 700;
    font-size: 11px;
}

.contacts button:hover {
    background: #d26070;
    color: #fff;
}

.contacts button:active {
    background: #fff;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}

.contacts__discont h2 {
    margin-top: 0;
    margin-bottom: 17px;
    text-transform: uppercase;
    font-size: 16px;
}

.contacts__discont label {
    display: block;
    color: #000000;
    font-size: 14px;
    font-weight: 300;
    margin-bottom: 20px;
}

.contacts__discont input {
    height: 45px;
    border: 1px solid #eaeaea;
    background-color: #ffffff;
    width: 100%;
    color: #b1b1b1;
    font-size: 13px;
    font-weight: 300;
    padding: 13px;
    font-family: inherit;
    outline: none;
    box-sizing: border-box;
    margin-bottom: 25px;
}

.contacts__discont input:focus {
    outline: none;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}

.contacts__discont input::-webkit-input-placeholder {
    /* Chrome/Opera/Safari */
    color: #b1b1b1;
}

.contacts__discont input::-moz-placeholder {
    /* Firefox 19+ */
    color: #b1b1b1;
}

.contacts__discont input:-ms-input-placeholder {
    /* IE 10+ */
    color: #b1b1b1;
}

.contacts__discont input:-moz-placeholder {
    /* Firefox 18- */
    color: #b1b1b1;
}

.contacts__discont button {
    padding: 12px 15px;
    border: 1px solid #eaeaea;
    background: white;
    font-family: inherit;
    text-transform: uppercase;
    color: #4a4a4a;
    font-weight: 700;
    font-size: 11px;
}

.contacts__discont button:hover {
    background: #d26070;
    color: #fff;
}

.contacts__discont button:active {
    background: #fff;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}
.contacts__discont {
  margin-right: 38px;
}
.contacts__total {
    width: 360px;
    background-color: #f5f3f3;
    padding: 43px;
    box-sizing: border-box;
    height: 214px;
}

.contacts__sub {
    margin-bottom: 9px;
    color: #4a4a4a;
    font-size: 11px;
    font-weight: 400;
    text-transform: uppercase;
    text-align: right;
}

.contacts__sub span:last-child {
    margin-left: 15px;
}

.contacts__grand {
    text-align: right;
    color: #222222;
    font-size: 16px;
    font-weight: 700;
    text-transform: uppercase;
    padding-bottom: 0px;
    border-bottom: 1px solid #e2e2e2;
    margin-bottom: 18px;
    display: flex;
    float: right;
}

.contacts__grand span:last-child {
    color: #f16d7f;
    margin-left: 20px;
    margin-top: -16px;
}
.contacts__grandBtn {
  letter-spacing: -0.01em;
  margin-bottom: -40px;
}

.contacts__total button {
    width: 100%;
    background-color: #f16d7f;
    padding: 13px 38px;
    text-align: center;
    color: #fff;
    text-transform: uppercase;
    font-size: 16px;
    font-weight: 700;
    border: none;
}

.contacts__total button:hover {
    background: #d26070;
    color: #fff;
}

.contacts__total button:active {
    background: #fff;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}

.contacts__grand_first {
    letter-spacing: 0.02em;
    margin-right: -5px;
}

.contacts {
    padding-bottom: 75px;
}
.contactsWrap {
  display: flex;
}
.adresWrap {
  width: 354px;
  margin-right: 38px;
}
.productsCart {
   display: flex;
}
.products {
    padding-bottom: 9px;
    border-bottom: 1px solid #eaeaea;
    font-weight: 700;
    text-transform: uppercase;
    font-size: 13px;
    color: #222222;
}

.products__title {
    font-size: 13px;
    margin-right: 350px;
    letter-spacing: 0;
    float: left;
    letter-spacing: -0.05em;
}

.products__navigation {
    max-width: 640px;
    display: flex;
}

.products__navigation li:nth-child(1) {
    margin-right: 95px;
}

.products__navigation li:nth-child(2) {
    margin-right: 76px;
}

.products__navigation li:nth-child(3) {
    margin-right: 85px;
}

.products__navigation li:nth-child(4) {
    margin-right: 50px;
}
.products__link {
  list-style-type: none;
}

</style>
