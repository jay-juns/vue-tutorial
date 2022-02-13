<template>
  <div class="modal__wrapper">
    <div class="overlay" @click="closeModal"></div>
    <div class="modal__container active">
      <div class="modal" :class="{ dark: theme === 'dark'}">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['theme'],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style>
  .overlay {
    width: 100%;
    height: 100%;
    position: fixed;
    left: 0;
    top: 0;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 102;
  }
  .modal__container {
    visibility: hidden;
    width: 100%;
    max-width: 600px;
    max-height: 90%;
    min-height: 300px;
    position: fixed;
    left: 50%;
    top: 50%;
    background-color: #fff;
    border-radius: 20px;
    padding: 20px;
    transform: translate(-50%, -50%);
    opacity: 0;
    animation: zoomOut 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
    transition: all 0.3s ease-out;
    z-index: 103;
    }
    .modal__container.active {
      visibility: visible;
      opacity: 1;
      animation: zoomIn 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
    }
    .modal {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    @keyframes zoomIn { 
      from { 
        transform: translate(-50%, 0) scale(0); 
      } 
      to { 
        transform: translate(-50%, -50%) scale(1); 
      } 
    }

    @keyframes zoomOut { 
      from { 
        transform: translate(-50%, -50%) scale(1); 
      } 
      to { 
        transform: translate(-50%, 0) scale(0); 
      } 
    }
</style>