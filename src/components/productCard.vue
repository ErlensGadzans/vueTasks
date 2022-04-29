<template>
  <div class="product-card">
    <img :src="imgUrl" />
    <div class="product card-info">
      <h2>{{ title }}</h2>
      <p class="price">Price: {{ price }} Euros</p>
      <p class="count">Available at the store: {{ count }} pcs.</p>
      <button type="button" @click="addToBasket">Add to basket</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "productCard",
  props: {
    title: String,
    price: { type: Number, requrired: true },

    imgUrl: {
      type: String,
      default: "https://tsum.by/images/no-photo.png",
    },
    count: { type: Number, default: 0 },
  },
  methods: {
    addToBasket() {
      this.$emit("addToBasket");
    },
  },
};
</script>

<style>
.product-card {
  width: 300px;
}

.product-card img {
  width: 300px;
}
.product-card {
  border: 1px solid rgb(211, 211, 211);
  padding: 20px 15px;
}

.card__info {
  margin-top: 20px;
}

h2,
.price {
  font-weight: 500;
}
.count {
  color: rgb(143, 143, 143);
}
button {
  background-color: rgb(221, 56, 56);
  color: #fff;
  border: none;
  border-radius: 4px;
  padding: 8px 14px;
  display: block;
  cursor: pointer;
  margin-top: 20px;
}
</style>