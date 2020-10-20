<template>
  <div class='v-main-page'>
    <p>
      <router-link :to="{name: 'catalog'}" class="brandLink">
        to Catalog
      </router-link>
    </p>
    <section class="brand" id="brand">
      <div class="container">
        <div class="brand_offer">
          <h1>
            THE BRAND
          </h1>
          <p>OF LUXERIOUS
            <span>FASHION</span>
          </p>
        </div>   
      </div>
	</section>
  <div class="container">
		<div class="offers">
			<div class="offerMan">
				<img src="../../assets/photo1.jpg" alt="photo">
				<div class="label">
					<div class="labelTop">
						hot deal
					</div>
					<div class="labelBottom">for men</div>
				</div>
			</div>
			<div class="offerTrendy">
				<img src="../../assets/photo2.jpg" alt="photo">
				<div class="label">
					<div class="labelTop">
						luxirous & trendy
					</div>
					<div class="labelBottom">
						accesories
					</div>
				</div>
			</div>
			<div class="offerWomen">
				<img src="../../assets/photo3.jpg" alt="photo">
				<div class="label">
					<div class="labelTop">30% offer</div>
					<div class="labelBottom">women</div>
				</div>
			</div>
			<div class="offerKids">
				<img src="../../assets/photo4.jpg" alt="photo">
				<div class="label">
					<div class="labelTop">new arrivals</div>
					<div class="labelBottom">for kids</div>
				</div>
			</div>
		</div>
	</div>
  <section class="fetured" id="fetured">
		<div class="container">
			<div class="row">
				<div class="col-12">
					<h2 class="fetured_title">
						Fetured Items
					</h2>
					<p class="fetured_subtitle">
						Shop for items based on what we featured in this week
					</p>
				</div>
			</div>
		</div>
	</section>
  <section class="featured" id="featured">
		<div class="container featuredWrap">
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic1.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic2.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic3.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic4.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic5.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic6.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic7.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
					<div class="featuredItem">
						<div class="featuredImgWrap">
							<div class="featuredBuy">
								<button>
									<img src="../../assets/forma.png" alt="forma">
									Add to Cart
								</button>
							</div>
							<img class="featuredProduct" src="../../assets/pic8.jpg" alt="mango">
						</div>
						<div class="featuredNameAndPrice">
							<div class="featuredItemName">
								Mango People T-shirt
							</div>
							<div class="featuredItemPrice">$52.00</div>
						</div>
					</div>
		</div>
	</section>
  <section class="allProduct" id="allProduct">
		<div class="container">
					<button class="allProduct__btn btn d-flex">
          <p>Browse All Product</p>
						<img src="../../assets/arrow.png" alt="Arrow">
					</button>
		</div>
	</section>
  <section class="offer" id="offer">
		<div class="container offerWrap">
					<div class="offer__main">
						<h3>30%<span>OFFER</span></h3>
						<p>FOR WOMEN</p>
					</div>
					<div class="offer__content">
						<div class="offer__terms">
							<img src="../../assets/icon1.png" alt="icon">
							<div class="offer__wrapper">
								<h4>Free Delivery</h4>
								<p>Worldwide delivery on all. Authorit tively morph next-generation innov tion with
									extensive models.</p>
							</div>
						</div>
						<div class="offer__terms">
							<img src="../../assets/icon2.png" alt="icon" class="offer__img">
							<div class="offer__wrapper">
								<h4>Sales & discounts</h4>
								<p>Worldwide delivery on all. Authorit tively morph next-generation innov tion with
									extensive models.</p>
							</div>
						</div>
						<div class="offer__terms">
							<img src="../../assets/icon3.png" alt="icon">
							<div class="offer__wrapper">
								<h4>Quality assurance</h4>
								<p class="offer__text">Worldwide delivery on all. Authorit tively morph next-generation
									innov tion with extensive models.</p>
							</div>
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
  export default {
    name: "v-main-page",
    props: {},
    data() {
      return {}
    },
    computed: {}
  }
</script>

<style lang="scss">
.brandLink {
    text-transform: uppercase;
    text-decoration: none;
    color: #222;
    font-weight: 700;
}
.brandLink:hover {
    color: #f16d7f;
}
.brand {
    padding-top: 195px;
    padding-bottom: 283px;
    background: #e8e8e8 url(../../assets/man.png) no-repeat 50% 90%;
}
.brand_offer {
    position: relative;
    margin-left: -500px;
    color: #222;
}

.brand_offer:before {
    content: "";
    width: 12px;
    height: 92px;
    background: #f16d7f;
    position: absolute;
    top: 27.5px;
    right: 67%;
}

.brand_offer h1 {
    font-size: 60px;
    font-weight: 900;
    margin-bottom: -50px;
    margin-left: -150px;
}

.brand_offer p {
    font-size: 40px;
    font-weight: 900;
    letter-spacing: 0.02em;
    margin-left: 24px;
}

.brand_offer span {
    font-size: 40px;
    font-weight: 900;
    color: #f16d7f;
}
.offers {
    margin-top: 100px;
    min-height: 829px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: repeat(3, 261px);
    grid-gap: 20px;

}

.offerMan {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 3;
}

.offerTrendy {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 3;
    grid-row-end: 4;
}

.offerWomen {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
}

.offers > div {
    position: relative;
}

.offers .label {
    position: absolute;
    top: 25px;
    padding: 15px 20px;
    background: white;
    text-transform: uppercase;
}

.labelTop {
    font-size: 18px;
    color: #222222;
    font-weight: 700;
}

.labelBottom {
    font-size: 30px;
    color: #f16d7f;
    font-weight: 900;
}
.fetured {
    padding-top: 85px;
    padding-bottom: 58px;
}
.featuredWrap {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-gap: 20px;
}
.fetured_title {
    font-size: 30px;
    font-weight: 700;
    text-align: center;
    margin-bottom: 0;
}

.fetured_subtitle {
    font-size: 14px;
    color: #9f9f9f;
    font-weight: 400;
    text-align: center;
    letter-spacing: 0.023em;
}
.featuredItems {
    margin-top: 60px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.featuredItem {
    width: 264px;
    height: 370px;
    margin-bottom: 31px;
}

.featuredItem:hover {
    box-shadow: 0 5px 8px rgba(0, 0, 0, 0.16);
}

.featuredItem:nth-child(n + 5) {
    margin-top: 27px;
}

.featuredImgWrap {
    height: 280px;
    position: relative;
}

.featuredBuy {
    height: inherit;
    width: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: none;
    position: absolute;
}

.featuredItem:hover .featuredBuy {
    display: flex;
    justify-content: center;
    align-items: center;
}

.featuredBuy button {
    padding: 15px;
    border: 1px solid #ffffff;
    background: none;
    color: white;
    font-size: 13px;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    height: 40px;
}

.featuredBuy button img {
    margin-right: 10px;
}

.featuredProduct {
    width: 100%;
    display: block;
    height: inherit;
    object-fit: cover;
    object-position: center center;
}

.featuredNameAndPrice {
    padding: 15px;
}

.featuredItemName {
    margin-bottom: 15px;
    font-size: 13px;
    text-transform: uppercase;
    color: #222222;
    font-weight: 700;
    max-height: 2.4em;
    overflow: hidden;
}

.featuredItemPrice {
    color: #f16d7f;
    font-size: 16px;
    font-weight: 700;
    text-transform: uppercase;
}
.allProduct {
    padding-top: 23px;
    padding-bottom: 111px;
}

.allProduct__btn {
    font-size: 16px;
    font-weight: 700;
    display: flex;
    margin: 0 auto;
    width: 211px;
    height: 48px;
    text-align: center;
    padding: 10px 16px 14px 24px;
}

.allProduct p {
    letter-spacing: 0;
    margin-top: 7px;
}

.allProduct img {
    margin-top: 10px;
    margin-left: 7px;
}
.offerWrap {
  display: flex;
}

.offer__main {
    background: url(../../assets/women.jpg) no-repeat center top/ cover;
    margin-bottom: 96px;
    width: 70%;
}

.offer__main h3 {
    padding-top: 122px;
    margin-left: -400px;
    margin-bottom: 20px;
    font-size: 54px;
    font-weight: 700;
    color: #fff;
    letter-spacing: 0.06em;
}

.offer__main span {
    color: #f16d7f;
}

.offer__main p {
    font-size: 32px;
    color: #fff;
    margin-left: -500px;
    padding-bottom: 295px;
    margin-top: -26px;
    letter-spacing: 0.02em;
}

.offer__content {
    background: #222224;
    padding-left: 36px;
    padding-right: 36px;
    height: 40%;
}

.offer__terms {
    padding-top: 46px;
}

.offer__terms {
    display: flex;
}

.offer__wrapper h4 {
    font-size: 20px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 10px;
    text-align: left;
}

.offer__wrapper p {
    font-size: 14px;
    font-weight: 300;
    color: #fff;
    line-height: 1.6em;
    letter-spacing: 0.015em;
    text-align: left;
}

.offer__terms img {
    margin-right: 30px;
    margin-top: 20px;
    height: 38px;
}

.offer__wrapper {
    width: 221px;
}

.offer__img {
    margin-right: 45px !important;
}

.offer__text {
    margin-bottom: 36px;
}
.subscribe {
    background: url(../../assets/bac.jpg) no-repeat center top/ cover, rgba(255, 255, 255, 0.4);
    background-blend-mode: color;
    height: 450px;
}
.subscribeWrap {
  display: flex;
}

.subscribe__text {
    font-size: 16px;
    color: #222224;
    font-style: italic;
    margin-bottom: 8px;
    font-weight: 700;
    letter-spacing: 0.04em;
    line-height: 1.6em;
}

.subscribe__content {
    max-width: 50%;
    margin-top: 7px;
    text-align: left;
}

.subscribe__content span {
    font-size: 16px;
    color: #f16d7f;
    font-weight: 700;
    letter-spacing: 0.02em;
}

.subscribe__bd {
    font-size: 12px;
    color: #222224;
    font-weight: 300;
    margin-top: 5px;
    letter-spacing: 0.02em;
}

.subscribe__bin img {
    height: 83px;
    margin-right: 28px;
    margin-top: 20px;
}

.subscribe__bin {
    // border-right: 1px solid #e3e3e3;
    height: 435px;
    padding-top: 112px;
    padding-bottom: 154px;
    display: flex;
}

.subscribe__reviews {
    width: 140px;
    display: flex;
    justify-content: space-between;
    margin-top: 40px;
}

.subscribe__reviews div {
    width: 38px;
    height: 4px;
    background-color: #d6d6d6;
}

.subscribe__reviews div:hover {
    background-color: #f16d7f;
    cursor: pointer;
}

.subscribe__title {
    font-size: 24px;
    font-weight: 400;
    color: #222224;
    text-transform: uppercase;
    text-align: center;
    margin-top: 25px;
}

.subscribe__our {
    font-size: 14px;
    font-weight: 400;
    color: #222224;
    text-transform: uppercase;
    text-align: center;
    margin-top: -8px;
    letter-spacing: 0;
    margin-bottom: 30px;
}

.subscribe__form {
    height: 46px;
    display: flex;
}

.subscribe__form input {
    height: inherit;
    width: 280px;
    border: none;
    outline: none;
    padding: 0 28px;
    font-weight: 400;
    background-color: #e1e1e1;
    border-top-left-radius: 23px;
    border-bottom-left-radius: 23px;
    float: left;
}

.subscribe__form button {
    background-color: #f16d7f;
    border-top-right-radius: 23px;
    border-bottom-right-radius: 23px;
    color: white;
    border: none;
    height: inherit;
    padding: 0 20px;
    outline: none;
    cursor: pointer;
}

.subscribe__form button:hover {
    background: #d26070;
    color: #fff;
}

.subscribe__form button:active {
    background: #fff;
    color: #f16d7f;
    border: 1px solid #f16d7f;
}

.subscribe__wrapper {
    margin-left: 91px;
    margin-top: 138px;
    max-width: 390px;
}
.company {
    padding-top: 111px;
    padding-bottom: 73px;
}
.compWr {
  display: flex;
}

.company__brand {
    width: 427px;
    font-size: 14px;
    font-weight: 300;
    line-height: 24px;
    color: #939393;
    margin-right: 100px;
}

.company__text_first {
    margin-top: 27px;
    letter-spacing: 0.02em;
    line-height: 1.6em;
    margin-bottom: 30px;
    text-align: left;
}

.company__text_second {
    letter-spacing: 0.02em;
    line-height: 1.6em;
    text-align: left;
}

.companyWrap {
  display: flex;
}

.company__column {
    padding-top: 15px;
    text-align: left;
}

.company__column h2 {
    font-size: 18px;
    font-weight: 700;
    color: #f16d7f;
    margin-top: -5px;
    margin-bottom: 28px;
}

.company__column a {
    display: block;
    color: #898989;
    font-size: 16px;
    text-decoration: none;
    margin-bottom: 18px;
    letter-spacing: 0.01em;
}

.company__column a:hover {
    color: #f16d7f;
}

.company__column_second {
    margin-left: 90px;
}

.company__column_third {
    margin-left: 90px;
}
.footerWrap {
  display: flex;
  justify-content: space-between;
  
}
.footer {
    padding-top: 26px;
    padding-bottom: 24px;
    background: #e6e6e6;
}

.copyrights__first {
    color: #7a7a7a;
    display: flex;
    font-size: 16px;
    font-weight: 400;
    letter-spacing: 0.03em;
    margin-top: 8px;
}

.copyrights__second {
    display: flex;
    width: 200px;
    justify-content: space-between;
    float: right;
}

.copyrights__second a {
    text-decoration: none;
    color: #b2b2b2;
}

.copyrights__second a {
    width: 32px;
    height: 32px;
    background: white;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.copyrights__second a:hover {
    color: white;
    background: #f16d7f;
}

</style>
