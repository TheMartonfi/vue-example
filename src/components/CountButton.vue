<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  initialCounter: {
    type: Number,
    required: true,
  },
  step: {
    type: Number,
    default: 1
  },
});

const count = ref(props.initialCounter);

const increment = () => {
  count.value += props.step;
};

const decrement = () => {
  count.value -= props.step;
};

onMounted(() => {
  increment();
});
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
