<template>
  <div class='v-catalog'>

    <v-notification
        :messages="messages"
    />


    <router-link :to="{name: 'cart', params: {cart_data: CART}}">
      <div class="v-catalog__link_to_cart">Cart: {{CART.length}}</div>
    </router-link>
    <h1>Catalog</h1>
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
    <div class="container">
    <div class="wraperAll">
                    <div class="trendingWrap">
                            <div class="products__paramHead">Trending now</div>
                            <nav class="trending__paramsWrap">
                                <a href="#">Bohemian</a>
                                <a href="#">Floral</a>
                                <a href="#">Lace</a>
                                <a href="#">Floral</a>
                                <a href="#">Lace</a>
                                <a href="#">Bohemian</a>
                            </nav>
                        </div>
                        <div class="sizesWrap">
                            <div class="products__paramHead">Size</div>
                            <div class="sizes__wrap">
                                <div>
                                    <input id="xxs" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="xxs">XXS</label>
                                </div>
                                <div>
                                    <input id="xs" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="xs">XS</label>
                                </div>
                                <div>
                                    <input id="s" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="s">S</label>
                                </div>
                                <div>
                                    <input id="m" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="m">M</label>
                                </div>
                                <div>
                                    <input id="l" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="l">L</label>
                                </div>
                                <div>
                                    <input id="xl" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="xl">XL</label>
                                </div>
                                <div>
                                    <input id="xxl" type="checkbox" name="size">
                                    <span class="products__checkbox"></span>
                                    <label for="xxl">XXL</label>
                                </div>
                            </div>
                        </div>
                        <div class="price__params">
                            <div class="products__paramHead">Price</div>
                            <div class="range-slider">
        <input
            type="range"
            min="0"
            max="1000"
            step="10"
            v-model.number="minPrice"
            @change="setRangeSlider"
        >
        <input
            type="range"
            min="0"
            max="10000"
            step="10"
            v-model.number="maxPrice"
            @change="setRangeSlider"
        >
      </div>
      <div class="range-values price__rangeValues">
        <p>${{minPrice}}</p>
        <p>${{maxPrice}}</p>
      </div>
    </div>
    </div>
    <form class="sorter">
    <div class="filters filtersWr">
      <v-select
          :selected="selected"
          :options="categories"
          @select="sortByCategories"
      />
    </div>
                        <div class="sorter__unit">
                            <label for="sort__by">Sort By</label>
                            <select name="select" id="sort__by">
                                <option value="vs1">Name</option>
                                <option value="vs2">Price</option>
                            </select>
                        </div>

                        <div class="sorter__unit">
                            <label for="show">Show</label>
                            <select name="select" id="show">
                                <option value="vs1">09</option>
                                <option value="vs2">08</option>
                                <option value="vs3">07</option>
                            </select>
                        </div>
                    </form>
    </div>
    <div class="v-catalog__list">
      <v-catalog-item
          v-for="product in filteredProducts"
          :key="product.article"
          :product_data="product"
          @addToCart="addToCart"
          @productClick="productClick"
      />
    </div>
    <div class="container">
    <div class="pagination__wrap">
                        <nav class="products__pagination">
                            <a href="#">
                                <i class="fas fa-chevron-left"></i>
                            </a>
                            <a href="">1</a>
                            <a href="">2</a>
                            <a href="">3</a>
                            <a href="">4</a>
                            <a href="">5</a>
                            <span>
                                <a href="">6</a>
                                .....
                                <a href="">20</a>
                            </span>
                            <a href="">
                                <i class="fas fa-chevron-right"></i>
                            </a>
                        </nav>
                        <button>View All</button>
                    </div>
                    </div>
    <section class="free" id="free">
        <div class="container freeBox">
            
                <div class="freeWrap">
                    <img src="../../assets/icon1.png" alt="icon">
                    <h2 class="free__title">Free Delivery</h2>
                    <p class="free__text free__text_first">
                        Worldwide delivery on all. Authorit
                        tively morph next-generation innov
                        tion with extensive models.
                    </p>
                </div>
                <div class="freeWrap">
                    <img src="../../assets/icon2.png" alt="icon">
                    <h2 class="free__title">Sales & discounts</h2>
                    <p class="free__text free__text_second">
                        Worldwide delivery on all. Authorit
                        tively morph next-generation innov
                        tion with extensive models.
                    </p>
                </div>
                <div class="freeWrap">
                    <img src="../../assets/icon3.png" alt="icon">
                    <h2 class="free__title">Quality assurance</h2>
                    <p class="free__text">
                        Worldwide delivery on all. Authorit
                        tively morph next-generation innov
                        tion with extensive models.
                    </p>
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
  import vCatalogItem from './v-catalog-item'
  import {mapActions, mapGetters} from 'vuex'
  import vSelect from '../v-select'
  import vNotification from '../notifications/v-notification'

  export default {
    name: "v-catalog",
    components: {
      vCatalogItem,
      vSelect,
      vNotification
    },
    props: {},
    data() {
      return {
        categories: [
          {name: 'Все', value: 'ALL'},
          {name: 'Мужские', value: 'м'},
          {name: 'Женские', value: 'ж'},
        ],
        selected: 'Все',
        sortedProducts: [],
        minPrice: 0,
        maxPrice: 10000,
        messages: []
      }
    },
    computed: {
      ...mapGetters([
        'PRODUCTS',
        'CART',
        'IS_MOBILE',
        'IS_DESKTOP',
        'SEARCH_VALUE'
      ]),
      filteredProducts() {
        if (this.sortedProducts.length) {
          return this.sortedProducts
        } else {
          return this.PRODUCTS
        }
      },
    },
    methods: {
      ...mapActions([
        'GET_PRODUCTS_FROM_API',
        'ADD_TO_CART'
      ]),
      productClick(article) {
        this.$router.push( {name: 'product', query: { 'product': article }})
      },
      setRangeSlider() {
        if (this.minPrice > this.maxPrice) {
          let tmp = this.maxPrice;
          this.maxPrice = this.minPrice;
          this.minPrice = tmp;
        }
        this.sortByCategories()
      },
      sortByCategories(category) {
        let vm = this;
        this.sortedProducts = [...this.PRODUCTS]
        this.sortedProducts = this.sortedProducts.filter(function (item) {
          return item.price >= vm.minPrice && item.price <= vm.maxPrice
        })
        if (category) {
          this.sortedProducts = this.sortedProducts.filter(function (e) {
            vm.selected === category.name;
            return e.category === category.name
          })
        }
      },
      addToCart(data) {
        this.ADD_TO_CART(data)
          .then(() => {
            let timeStamp = Date.now().toLocaleString();
            this.messages.unshift(
              {name: 'Товар добавлен в корзину', icon: 'check_circle', id: timeStamp}
            )
          })
      },
      sortProductsBySearchValue(value) {
        this.sortedProducts = [...this.PRODUCTS]
        if (value) {
          this.sortedProducts = this.sortedProducts.filter(function (item) {
            return item.name.toLowerCase().includes(value.toLowerCase())
          })
        } else {
          this.sortedProducts = this.PRODUCTS;
        }
      }
    },
    watch: {
      SEARCH_VALUE() {
        this.sortProductsBySearchValue(this.SEARCH_VALUE);
      }
    },
    mounted() {
      this.GET_PRODUCTS_FROM_API()
        .then((response) => {
          if (response.data) {
            this.sortByCategories()
            this.sortProductsBySearchValue(this.SEARCH_VALUE)
          }
        })
    }
  }
</script>

<style lang="scss">

  .v-catalog {
    &__list {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
    }

    &__link_to_cart {
      position: absolute;
      top: 45px;
      right: 190px;
      padding: 15px;
      border: none;
      background: #ffffff;
      border-radius: 5px;
    }
  }

  .filters {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .range-slider {
    width: 200px;
    margin: auto 16px;
    text-align: center;
    position: relative;
    margin-top: 40px;
  }

  .range-slider svg, .range-slider input[type=range] {
    
    position: absolute;
    left: 0;
    bottom: 0;
  }

  input[type=range]::-webkit-slider-thumb {
    z-index: 2;
    position: relative;
    top: 2px;
    margin-top: -7px;
  }
  .v-catalog__list {
    max-width: 1140px;
    margin-left: 180px;
  }
  .arrivals {
    padding-top: 53px;
    padding-bottom: 50px;
    background: #f8f3f4;
    text-transform: uppercase;
    margin-bottom: 50px;
}
.arrivalsWrap {
  display: flex;
  justify-content: space-between;
}

.arrivals__title {
    font-size: 24px;
    font-weight: 900;
    color: #f16d7f;
    letter-spacing: 0;
}

.arrivals__navigation {
    margin-left: 64px;
    margin-top: 30px;
}

.arrivals__navigation a {
    text-decoration: none;
    color: #636363;
}

.arrivals__navigation a:hover {
    color: #f16d7f;
}
  .products__paramHead {
  color: #6f6e6e;
  font-size: 14px;
  font-weight: 700;
  text-transform: uppercase;
  margin-bottom: 15px;
}
.trendingWrap {
  width: 350px;
  margin-right: 30px;
}

.trending__paramsWrap {
  color: #6f6e6e;
  font-size: 14px;
  text-transform: none;
  font-weight: 400;
  flex-wrap: wrap;
  width: 150px;
}

.trending__paramsWrap a {
  color: #6f6e6e;
  padding-left: 7px;
  text-decoration: none;
}

.trending__paramsWrap a:after {
  content: "|";
  margin-left: 7px;
  color: #dfdfdf;
}

.trending__paramsWrap a:last-child:after {
  display: none;
}
.sizes__wrap {
  overflow: hidden;
  width: 380px;
  margin-right: 50px;
}

.sizes__wrap > div {
  float: left;
  width: 63px;
}

.sizes__wrap > div .products__checkbox {
  display: inline-block;
  width: 13px;
  height: 13px;
  background: url(../../assets/checkbox.png) no-repeat;
}

.sizes__wrap > div input[type="checkbox"] {
  display: none;
}

.sizes__wrap > div input[type="checkbox"]:checked + .productsCheckbox {
  background: url(../../assets/checkbox.png) no-repeat, url(../../assets/check-solid.svg) no-repeat;
  background-size: contain, 12px;
  background-blend-mode: multiply;
}

.sizes__wrap > div label {
  margin-bottom: auto;
  cursor: pointer;
  color: #6f6e6e;
  margin-left: 8px;
}
.price__params img {
  width: 100%;
}

.price__params .price__rangeValues {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  color: #6f6e6e;
  font-size: 14px;
  margin-top: 12px;
  width: 320px;
}
.wraperAll {
  display: flex;
}
.sorter {
  padding: 10px;
  background-color: #f3f3f3;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-line-pack: center;
      align-content: center;
  margin-top: 33px;
  margin-bottom: 60px;
}

.sorter .sorter__unit {
  border: 1px solid #ebebeb;
  border-radius: 4px;
  background: #ffffff;
  height: 30px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.sorter .sorter__unit:first-child {
  margin-right: 10px;
}

.sorter .sorter__unit label {
  margin-bottom: auto;
  border-right: 1px solid #ebebeb;
}

.sorter .sorter__unit label,
.sorter .sorter__unit select {
  color: #6f6e6e;
  font-size: 14px;
  font-weight: 400;
  height: 100%;
  line-height: 27px;
  padding-left: 10px;
  padding-right: 10px;
  display: block;
}

.sorter .sorter__unit select {
  border: none;
  outline: none;
  padding-bottom: 2px;
  -webkit-appearance: none;
  -moz-appearance: none;
  background: url(../../assets/caret-down-solid.svg) no-repeat right 5px center;
  background-size: 9px;
  padding-right: 20px;
}
.filtersWr {
  background: #fff;
  color: #6f6e6e;
}
.pagination__wrap {
  margin-top: 40px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  -webkit-box-align: start;
      -ms-flex-align: start;
          align-items: flex-start;
  color: #c4c4c4;
  border-top: 1px solid #ebebeb;
  padding-top: 50px;
  
}

.pagination__wrap .products__pagination {
  border-radius: 3px;
  border: 1px solid #ebebeb;
  width: 261px;
  height: 44px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: space-evenly;
      -ms-flex-pack: space-evenly;
          justify-content: space-evenly;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}

.pagination__wrap .products__pagination i {
  font-size: 12px;
}

.pagination__wrap .products__pagination a {
  color: inherit;
  font-size: 16px;
  font-weight: 300;
}

.pagination__wrap .products__pagination a:hover {
  color: #ef5b70;
}

.pagination__wrap button {
  font-size: 16px;
  font-weight: 300;
  width: 150px;
  line-height: 43px;
  border-radius: 3px;
  border: 1px solid #ef5b70;
  text-align: center;
  color: #ef5b70;
  background: none;
  cursor: pointer;
}

.pagination__wrap button:hover {
  background: #ef5b70;
  color: #fff;
}
  .free {
  margin-top: 70px;
  background: #222224;
  padding-top: 90px;
  padding-bottom: 110px;
  color: #fbfbfb;
}
.freeBox {
  display: flex;
  margin-left: 220px;
}
.freeWrap {
  margin-right: 50px;
}

.free div[class^="col-"] {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
}

.free .free__title {
  color: #fbfbfb;
  margin-top: 20px;
  margin-bottom: 8px;
  font-size: 20px;
  font-weight: 700;
}

.free .free__text {
  width: 309px;
  font-weight: 300;
  text-align: justify;
  letter-spacing: 0.02em;
  line-height: 1.7em;
}
</style>
