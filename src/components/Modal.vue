<template>
  <div class="backdrop">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>default slot</slot>

      <div class="actions">
        <slot name="links"></slot>
      </div>
      <button class="btn" @click="closeModal">Close Modal</button>
      <button class="btn_2" @click="changeSale">Sale</button>
    </div>
  </div>
</template>
<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
    changeSale() {
      this.$emit("isSale");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 115px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.3);
  width: 100%;
  height: 100%;
}
.modal .actions a {
  text-decoration: none;
  padding: 1px;
  border: 1px solid black;
  border-radius: 5px;
  color: rgb(8, 8, 4);
  margin: 5px;
}
.modal.sale .actions a {
  text-decoration: none;
  padding: 1px;
  border: 1px solid rgb(182, 26, 26);
  border-radius: 5px;
  color: rgb(182, 26, 26);
  margin: 5px;
}
.modal .btn {
  padding: px;
  color: rgb(8, 8, 4);
  margin: 10px;
}

.modal.sale {
  background: rgb(255, 0, 0);
  color: rgb(255, 255, 255);
}
</style>