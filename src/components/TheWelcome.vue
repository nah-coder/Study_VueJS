<script setup>
const props = defineProps(['countView']);
const emit = defineEmits(['handle-increase']);

const onIncrease = () => {
  emit('handle-increase');
};
</script>

<template>
  <div class="red">
    <h1>Count : {{ props.countView }}</h1>
    <button @click="onIncrease">increase</button>
  </div>
</template>


