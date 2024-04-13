<script setup>
export default {
  props: {
    initialCounter: {
      type: Number,
      required: true,
    },
    step: {
      type: Number,
      default: 1
    },
  },
  data() {
    return {
      count: this.initialCounter,
    }
  },
  methods: {
    increment() {
      this.count++
    },
    decrement() {
      this.count--
    },
  },
  mounted() {
    // methods can be called in lifecycle hooks, or other methods!
    this.increment()
  }
}
</script>

<template>
  <div>
    <button class="count-button" v-if="count < 10" @click="increment">{{ count }}</button>
    <button class="count-button" v-else-if="count >= 10" @click="decrement">{{ count }}</button>
    <p v-else>Default case</p>
  </div>
</template>

<style scoped>
.count-button {
  width: fit-content;
  height: 24px;
}
</style>
