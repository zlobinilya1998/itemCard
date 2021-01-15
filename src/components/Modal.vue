<template>
  <div class="modal" data-remodal-id="modal" role="dialog">
    <div class="">
      <form target=".card" name="modal" method="GET" class="modal__form">
        <div class="modal__close">
          <h2 id="modal__title">
            Модальное окно
          </h2>
          <a class="close" @click="closeModal" />
        </div>

        <input type="text" name="name" placeholder="Ваше имя" required />
        <input type="tel" name="phone" placeholder="Номер телефона" required />
        <input type="email" name="email" placeholder="E-mail" required />
        <input
          type="text"
          name="text"
          placeholder="Название товара"
          required
          :value="product.name"
        />
        <button type="submit" name="submit" class="btn" value="ОТПРАВИТЬ">
          Отправить
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: {
    product: Object,
  },
  methods: {
    closeModal() {
      this.$emit("closeModal");
    },
  },
};
</script>

<style>
.modal {
  position: absolute;
  left: 35%;
  top: 35%;
  padding: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: palegoldenrod;
  width: 400px;
  transition: all 0.5s;
  border: 2px sandybrown solid;
}
h2 {
  margin: 0 !important;
}
.modal__icon {
  background-image: url("../assets/close.svg");
  background-size: cover;
  width: 15px;
  height: 15px;
}
.modal__close {
  display: flex;
  align-items: center;
  flex-direction: row;
  margin-bottom: 10px;
}
.modal__form {
  display: flex;
  flex-direction: column;
}
input {
  margin-bottom: 8px;
}
.close {
  position: absolute;
  right: 5px;
  top: 8px;
  width: 25px;
  height: 25px;
  opacity: 0.3;
  cursor: pointer;
}
.close:hover {
  opacity: 1;
}
.close:before,
.close:after {
  position: absolute;
  content: " ";
  height: 25px;
  width: 2px;
  background-color: #333;
}
.close:before {
  transform: rotate(45deg);
}
.close:after {
  transform: rotate(-45deg);
}
</style>
