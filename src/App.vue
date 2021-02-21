<template>
  <div id="app">
    <div>
      <b-navbar type="dark" variant="Success">
          <router-link to="/" class="container">
            <b-nav-item href="/">CS Shop</b-nav-item>
          </router-link>
        
        <b-navebar-nav class="ml-auto">
          <div>
            <router-link to="/About">
              <b-button variant="outline-info" @click="sum">
                <b-icon icon="basket" aria-hidden="ture"></b-icon>
              </b-button>
            </router-link>
          </div>
        </b-navebar-nav>
      </b-navbar>
    </div>
    <router-view
      :cardList="cardList"
      :product="product"
      @update-cart="UpProduct"
      :tprice="tprice"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      cardList: [
        {
          nameProduct: "Gaming Keyboard Feeling RGB",
          price:19000,
          img: "https://cf.shopee.co.th/file/10165b8878e0bf4278ce046c860436c4",
          txt:""
          
        },
        {
          img:
            "https://ae01.alicdn.com/kf/HLB1mrcvae3tHKVjSZSgq6x4QFXak/LED-Light-Gaming-Mouse-1600DPI-USB-Charger-X7.jpg",
          price: 450,
          txt:"",
          nameProduct: "LED-Light-Gaming-Mouse",
        },
        {
          img: "https://cf.shopee.co.th/file/3c89bfc7b67d54e1f5911c2ca4000376",
          price: 2500,
          txt:"",
          nameProduct: "หูฟังเกมมิ่ง Logitech รุ่น G633s 7.1 Surroundw",
        },
        {
          img:
            "https://mercular.s3.ap-southeast-1.amazonaws.com/images/products/2020/09/XG32VQR-1.jpg",
          price: 2500,
          txt:"",
          nameProduct: "Asus ROG XG32VQR 31.5 Monitor 144Hz",
        },
        {
          img:
            "https://mercular.s3.ap-southeast-1.amazonaws.com/images/products/2020/10/TORQUE-BLACKWHITE-Case-1.jpg",
            price: 12900,
            txt:"",
          nameProduct: "ANTEC TORQUE White Computer Case",
        },
        {
          img:
            "https://www.jib.co.th/img_master/product/original/2019061315310834108_1.jpg",
          price: 32000,
          txt:"",
          nameProduct: "ASUS ROG STRIX HERO III G531GW-A",
        },
      ],
      product: [],
      tprice: 0,
    };
  },
  methods: {
    UpProduct(value) {
      this.product.push(value);
    },
    sum() {
      this.tprice = 0;
      for (var i = 0; i < this.product.length; i++) {
        this.tprice = this.tprice + this.product[i].price;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
