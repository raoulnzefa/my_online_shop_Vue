<template>
  <div class="container">
    <div class='v-header header'>
      <router-link :to="{name: 'mainPage'}" class="logo">
        <img src="../../assets/logo.png" alt="">
        <p>BRAN
            <span>D</span>
        </p>
      </router-link>
      <div class="search-field form">
        <div class="form_select d-flex">
          <p>Browse</p>
          <i class="fas fa-caret-down"></i>
        </div>               
        <input
            type="text"
            v-model="searchValue"
            placeholder="Search for Item..."
            class="form_input"
        >
        <button class="search_btn form_button">
          <i class="material-icons" @click="search(searchValue)">search</i>
        </button>
        <button class="search_btn">
          <i class="material-icons" @click="clearSearchField">cancel</i>
        </button>
      </div>
    </div>
    <section class="menu" id="menu">
        <div class="container">
          <ul class="menu_wrapper">
            <li class="menu_link">
              <a href="#">Home</a>
            </li>
            <li class="menu_link">
              <a href="#">Man</a>
            </li>
            <li class="menu_link">
              <a href="#">Women</a>
            </li>
            <li class="menu_link">
              <a href="#">Kids</a>
            </li>
            <li class="menu_link">
              <a href="#">Accoseriese</a>
            </li>
            <li class="menu_link">
              <a href="#">Featured</a>
            </li>
            <li class="menu_link">
              <a href="#">Hot Deals</a>
            </li>
          </ul>                   
        </div>
    </section>
  </div>
</template>

<script>
  import {mapActions, mapGetters} from 'vuex'

  export default {
    name: "v-header",
    props: {},
    data() {
      return {
        searchValue: ''
      }
    },
    computed: {
      ...mapGetters([
        'SEARCH_VALUE'
      ])
    },
    methods: {
      ...mapActions([
        'GET_SEARCH_VALUE_TO_VUEX'
      ]),
      search(value) {
        this.GET_SEARCH_VALUE_TO_VUEX(value);
        if (this.$route.path !== '/catalog') {
          this.$router.push('/catalog')
        }
      },
      clearSearchField() {
        this.searchValue = ''
        this.GET_SEARCH_VALUE_TO_VUEX();
        if (this.$route.path !== '/catalog') {
          this.$router.push('/catalog')
        }
      }
    }
  }
</script>

 <style lang="scss">

 .container {
	max-width: 1140px;
	margin: 0 auto;
}
.header {
    padding-bottom: 24px;
    border-bottom: 1px solid #ececec;
    width: 100%;
    display: flex;
    margin-top: -110px;
}
.logo {
    height: 51px;
    display: flex;
    text-decoration: none;
    margin-right: 150px;
}

.logo p {
    font-size: 27px;
    font-weight: 300;
    margin-left: 11px;
    color: #222;
    align-items: center;
    margin-top: 11px;
    display: flex;
    margin-top: 30px; 
}

.logo span {
    font-weight: 700;
    color: #f16d7f;
}
.form {
  display: flex;
}
input {
    width: 280px;
    height: 38px;
    border: 1px solid #e6e6e6;
    padding-left: 16px;
    outline: none;
    color: #ababab;
}
input::-webkit-input-placeholder {
    color: inherit;
    opacity: 1;
    -webkit-transition: all 0.2s ease;
    transition: all 0.2s ease;
}

input:focus {
    outline: none;
    color: #f16d7f;
    border: 1px solid #f16d7f;
    height: 37px;
}

.form_input:-moz-placeholder {
    color: inherit;
    opacity: 1;
    -webkit-transition: all 0.2s ease;
    transition: all 0.2s ease;
}

input::-moz-placeholder {
    color: inherit;
    opacity: 1;
    -webkit-transition: all 0.2s ease;
    transition: all 0.2s ease;
}

input:-ms-input-placeholder {
    color: inherit;
    opacity: 1;
    -webkit-transition: all 0.2s ease;
    transition: all 0.2s ease;
}

input:active {
    background: #f9f9f9;
}
.form_select {
    border: 1px solid #e6e6e6;
    background: #f9f9f9;
    display: inline-block;
    display: flex;
    padding: 0px 6px 2px 14px;
    width: 87px;
    height: 38px;
    border-right: none;
    cursor: pointer;
}

.form_select .fa-caret-down {
    color: #838383;
    margin-top: 14px;
}

.form_select p {
    margin-right: 7px;
    margin-top: 13px;
}
.search_btn {
width: 36px;
    border-left: none;
    display: block;
    text-align: center;
    padding-top: 10px;
    border: 1px solid #e6e6e6;
    outline: none;
    height: 42px;
    color: #a4a4a4;
    cursor: pointer;
}
.search_btn:hover {
    color: #f16d7f;
}
.menu {
    /*padding-top: 14px;
    padding-bottom: 17px;*/
    height: 51px;
}

.menu_wrapper {
    text-align: center;
    margin: 0 auto;
    max-width: 700px;
    padding-top: 15px;
    min-height: 51px;
    display: flex;
}

.menu_link a {
    font-size: 14px;
    font-weight: 700;
    color: #222;
    text-transform: uppercase;
    display: block;
    padding-left: 18px;
    padding-right: 18px;
    text-decoration: none;
    
}

.menu_link {
    margin-right: 21px;
    margin-left: -15px;
    list-style-type: none !important;
}

.menu_link:last-child {
    margin-right: 0;
}

.menu_link a:hover {
    color: #f16d7f;
    border-bottom: 3px solid #ef5b70;
    padding-bottom: 13px;
}
</style>
