<template>
  <h1 id="title">{{ title }}</h1>
  <div v-if="showModal">
    <Modal :theme="theme" @close="showModals" @isSale="changeSales">
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">More Info</a>
      </template>
      <h1>My Prop Training</h1>
      <p>Hello Trainees, how you doing</p>
      <p>Hope you okay</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal :theme="theme" @close="showModalsTwo">
      <h1>Hello my friends again</h1>
      <p>Hope you doing great all time</p>
      <p>Have a nice day</p>
    </Modal>
  </div>
  <button @click="showModals">Show Modal</button>
  <button @click="showModalsTwo">Show Modal Two</button>
  <button class="btn_2" @click="changeSale">Sale</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },

  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModalTwo: false,
      theme: "sale",
    };
  },
  methods: {
    showModals() {
      this.showModal = !this.showModal;
    },
    showModalsTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
    changeSale() {
      if (this.theme == "sale") {
        this.theme = "unsale";
      } else {
        this.theme = "sale";
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
  margin-top: 60px;
}
</style>
