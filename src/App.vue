<template>
  <h1>
    {{ title }}
  </h1>
  <teleport to="#modalsPortal" v-if="showModal">
    <Modal :header="header" :text="text" theme="dark" @close="toggleModal">
        <h1>Sign up for the give away</h1>
        <p>Grab your blogs for half price!</p>
    </Modal>  
  </teleport>

  <teleport to="#modalsPortal" v-if="showModalTwo">
    <Modal :header="header" :text="text" theme="dark" @close="toggleModalTwo">
        <h1>Sign up to the newletters</h1>
        <p>For updates and promo codes!</p>
    </Modal>  
  </teleport> 

  <button @click="toggleModal">Open modal</button>
  <button @click="toggleModalTwo">Open modal Two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: '나의 첫번째 vue3',
      header: 'Sign up for the give away',
      text: 'Grab your blogs for half price!',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
        this.showModal = !this.showModal
    },
    toggleModalTwo() {
        this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
  #app {
  width: 100%;
  height: 100%;
  }
</style>
