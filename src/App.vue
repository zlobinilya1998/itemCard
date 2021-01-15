<template>
  <div class="wrapper">
    <Card
      @selectItem="currentItem"
      v-for="item in json"
      :key="item"
      :product="item"
    />
    <Modal @closeModal="closeModal" v-if="showModal" :product="selectedItem" />
  </div>
</template>

<script>
import json from "./assets/product.json";
import Modal from "./components/Modal";

import Card from "./components/Card";
export default {
  name: "App",
  components: {
    Card,
    Modal,
  },
  data() {
    return {
      selectedItem: null,
      json: json.product,
      showModal: false,
    };
  },
  methods: {
    openModal() {
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
    currentItem(item) {
      this.selectedItem = item;
      this.openModal();
    },
  },
};
</script>

<style>
#app {
  min-width: 100vh;
  min-height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.wrapper {
  display: flex;
  flex-wrap: wrap;
}
</style>
