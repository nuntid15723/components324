
Skip to content
Pull requests
Issues
Marketplace
Explore
@nuntid15723
masterpongpon /
tuushop

1
0

    1

Code
Issues
Pull requests
Actions
Projects
Wiki
Security

    Insights

tuushop/src/views/Home.vue
@masterpongpon
masterpongpon New
Latest commit f0997dc 5 hours ago
History
1 contributor
50 lines (48 sloc) 1.07 KB
<template>
  <div class="home">
    <b-container>
      <br />
      <b-row>
        <b-col cols="4" v-for="index in cardList" :key="index">
          <Product
            :img="index.img"
            :price="index.price"
            :nameProduct="index.nameProduct"
            @update-cart="sub"
          />
        </b-col>
      </b-row>
    </b-container>
    <b-modal id="bv-modal-example" hide-footer>
      <template #modal-title class="text-center">แจ้งเตือน!!</template>
      <div class="d-block text-center">
        <p>หยิบสินค้าเรียบร้อย!!</p>
      </div>
      <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')"
        >ปิด</b-button
      >
    </b-modal>
  </div>
</template>

<script>
// @ is an alias to /src
import Product from "@/components/user.vue";
export default {
  name: "Home",
  props: {
    cardList: Array
  },
  components: {
    Product
  },
  data() {
    return {
    
    };
  },
  methods: {
    sub(value) {
      this.$emit("update-cart", value);
    }
  }
};
</script>

    © 2021 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Docs

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

