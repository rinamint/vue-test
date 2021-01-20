<template>
  <div v-if="isVisible">
      <div class="modal">
        <header class="modal-header">
          <slot name="header">
            Наши преимущества:
            <button type="button" class="btn-close" v-on:click="emitCancel">
              <span> x </span>
            </button>
          </slot>
        </header>
        <section class="modal-body">
          <slot name="body">
            <p>
              Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
              reprehenderit in voluptateLorem ipsum dolor sit amet, consectetur
              adipiscing elit, sed do eiusmod tempor incididunt ut labore et
              dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
              exercitation ullamco laboris nisi ut aliquip ex ea commodo
              consequat. Duis aute irure dolor in reprehenderit in voluptate
            </p>
          </slot>
        </section>
        <footer class="modal-footer">
          <slot name="footer">
            <button type="button" class="btn-confirm" v-on:click="emitCancel">
              Все ясно
            </button>
          </slot>
        </footer>
      </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  methods: {
    emitCancel() {
      this.$emit("cancel");
    },
  },
  props: {
    isVisible: {
      type: Boolean,
      default: () => false,
    },
  },
};
</script>

<style>
.modal {
  display: flex;
  flex-direction: column;
  position: fixed;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -40%);
  z-index: 999;
  width: 70%;
  background: #ffffff;
  box-shadow: 2px 2px 20px 1px;

}

.modal-header,
.modal-footer {
  display: flex;
  padding: 15px;
}

.modal-header {
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #eeeeee;
}

.modal-footer {
  justify-content: flex-end;
  border-top: 1px solid #eeeeee;
}

.modal-body {
  padding: 20px 10px;
}

.btn-close {
  padding: 20px;
  border: none;
  font-size: 1.5em;
  font-weight: bold;
  color: #4aae9b;
  background: transparent;
}

.btn-confirm {
  border: 1px solid #808080;
  border-radius: 5px;
  color: #ffffff;
  background: #808080;
  font-size: 18px;

}
</style>
