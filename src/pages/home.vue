<template>
  <div class="body">
    <div id="app">
      <button @click="toggleBox">click here</button>
      <transition name="box-fade">
        <div class="box" v-if="isVisible">
          <h2>VueJS Version Updated to V3</h2>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return { isVisible: true }
  },
  methods: {
    toggleBox() {
      this.isVisible = !this.isVisible
    },
  },
}
</script>

<style>

.box {
  margin: 3rem auto;
  max-width: 40rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 2rem;
}

.box-fade-enter-from,
.box-fade-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}

.box-fade-enter-active,
.box-fade-leave-active {
  transition: all 0.3s ease;
}

.box-fade-enter-to,
.box-fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}
</style>
