<template>
  <div class="product-list">
    <h1>Tables</h1>
    <search @search="searchProducts" />

    <ul>
      <li
        style="list-style: none"
        v-for="(product, index) in products"
        :key="index"
      >
        <productCard
          :title="product.title"
          :price="product.price"
          :imgUrl="product.imgUrl"
          :count="product.count"
          @addToBasket="addToBasket(index)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import productCard from "./productCard.vue";
import search from "./search.vue";
export default {
  name: "taskFour",
  components: { productCard, search },
  data() {
    return {
      searchText: "",
      products: [
        {
          title: "Стол Jim",
          price: 19999,
          //   imgUrl:
          //     "https://hoff.ru/upload/iblock/8c9/8c989500ee8639b9e3aa267b1888b4af.jpg",
          count: 30,
        },
        {
          title: "Стол Monako",
          price: 17199,
          imgUrl:
            "https://hoff.ru/upload/iblock/af2/af2d37161f217d4f489373be7da4a7a0.jpg",
          count: 20,
        },
        {
          title: "Стол с двумя ящиками Кварт MD 768",
          price: 10999,
          imgUrl:
            "https://hoff.ru/upload/iblock/1cc/1ccb33b50e3e9cfa08629bf455e41855.jpg",
          count: 23,
        },
      ],
    };
  },
  methods: {
    addToBasket(index) {
      console.log(index);
    },
    searchProducts(searchText) {
      console.log("searched products" + searchText);
    },
  },
};
</script>


<style>
</style>