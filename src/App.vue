<template>
  <section class="teste">
    <nav id="nav">
      <div>
        <img src="/assets/img/logo.svg" alt="" width="200" />
      </div>
      <div>
        <ul class="navbar">
          <li v-for="(items, index) in navbar" :key="index">{{ items }}</li>
        </ul>
      </div>
      <div class="navbar-profile">
        <div class="content-profile">
          <div>
            <ion-icon name="cart-outline" size="large"></ion-icon>
          </div>
          <div class="image-profile">
            <img :src="imageProfile" alt="" width="50" />
          </div>
        </div>
      </div>
    </nav>
  </section>

  <section>
    <div class="container-principal">
      <div class="container-img">
        <img :src="item" alt="" width="500" />
        <div class="container-mini-imagem">
          <div class="teste-bg">
            <img
              @mousemove="changeItem1"
              @mouseleave="returnItem"
              :src="image2"
              alt=""
              width="80"
            />
          </div>
          <div>
            <img
              @mousemove="changeItem2"
              @mouseleave="returnItem"
              :src="image3"
              alt=""
              width="80"
            />
          </div>
          <div>
            <img
              @mousemove="changeItem3"
              @mouseleave="returnItem"
              :src="image4"
              alt=""
              width="80"
            />
          </div>
        </div>
      </div>
      <div class="text-principal">
        <div class="content-text">
          <p>SNEAKERS COMPANY</p>
          <h3>Fall Limited Edition Sneakers</h3>
          <span
            >Lorem Ipsum is simply dummy text of the printing and typesetting
            industry. Lorem Ipsum has been the industry's standard dummy text
            ever since the 1500s,
          </span>
        </div>
        <div class="container-prices">
          <div>
            <span>$125</span>
          </div>
          <span></span>
        </div>
        <div class="compras">
          <div class="container-compras">
            <button @click="incrementItem" class="button-decrement">
              <img @click="incrementItem()" src="/assets/img/subtracao.png" alt="" width="20">
            </button>
            <span class="text-price">{{ price  }}</span>
            <button @click="decrementItem()" class="button-increment">
              <img src="/assets/img/soma.png" alt="" width="20">
            </button>
            <div>
            <button class="button-cart">Add to cart</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "page ecommerce",
  components: {},
  data() {
    return {
      navbar: ["Colletions", "Men", "Women", "About", "Conta"],
      imageProfile: "/assets/img/profile.png",
      item: "/assets/img/bot1.jpg",
      image1: "/assets/img/bot1.jpg",
      image2: "/assets/img/boot2.jpg",
      image3: "/assets/img/boot3.jpg",
      image4: "/assets/img/boot4.jpg",
      price: 1
    };
  },
  methods: {
    changeItem1() {
      this.item = this.image2;
    },
    changeItem2() {
      this.item = this.image3;
    },
    changeItem3() {
      this.item = this.image4;
    },
    returnItem() {
      this.item === this.image1;
    },
    methods:{
      incrementPrice(){
        this.price = this.price + 1
      },
       decrementPrice(){
        this.price = this.price - 1
      }
    }
  },
};
</script>

<style scoped>
@import "./style.css";
</style>
