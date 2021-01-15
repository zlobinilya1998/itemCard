<template>
  <div class="card">
    <img class="card__img" :src="product.img" />
    <p class="card__text">{{ product.name }}</p>
    <p class="card__price">{{ product.price }} &#8381;</p>
    <button @click="selectItem(product)" class="card__btn">Купить</button>
  </div>
</template>

<script>
export default {
  name: "Card",
  data() {
    return {};
  },
  props: {
    product: Object,
  },
  methods: {
    selectItem(product) {
      this.$emit("selectItem", product);
    },
  },
};
</script>

<style>
.card {
  width: 200px;
  margin: 20px auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.card__text {
}
.card__img {
  width: min-content;
}
.card__btn {
  width: 75%;
  height: 35px;
  background: rgb(177, 44, 126);
  color: white;
  border-radius: 25px;
  transition: all 0.5s;
  outline: none;
}
.card__btn:hover {
  background: rgb(248, 75, 182);
}
</style>
