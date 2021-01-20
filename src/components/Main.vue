<template>
  <main class="main">
    <section class="section">
      <h1>Интересный заголовок</h1>
      <p class="blurry-text">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
        commodo consequat. Duis aute irure dolor in reprehenderit in
        voluptateLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
        eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
        minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip
        ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
        voluptate
      </p>
      <p class="main-text">
        Основной текст, рассказывающий о преимуществах предложения
      </p>
      <button v-on:click="ModalVisible = true" class="modal-btn">
        Нажми меня!
      </button>

      <Modal
        :isVisible="ModalVisible"
        v-on:cancel="ModalVisible = false"
      />
    </section>
    <div class="carousel">
      <Slick />
    </div>
  </main>
</template>

<script>
import Slick from "./Slick.vue";
import Modal from "./Modal.vue";

export default {
  name: "Main",
  components: {
    Slick,
    Modal,
  },
  data() {
    return {
      ModalVisible: false,
    };
  },
};
</script>

<style>
.main {
  display: flex;
  position: relative;
}
.section {
  min-width: 40%;
  position: relative;
}
.blurry-text {
  opacity: 0.1;
}
.main-text {
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -40%);
  font-weight: bold;
}
.modal-btn {
  font-size: 1.5em;
  padding: 10px;
  margin: 20px;
  background: #0d0d0d;
  color: #ffffff;
  font-weight: bold;
  border-radius: 15px;
}

.carousel {
  margin: auto;
  width: 60%;
}

@media only screen and (max-width: 992px), (max-width: 1200px) {
  .main {
    flex-direction: column;
  }
}



</style>
