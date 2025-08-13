<script setup>
const props = defineProps(['countView']);
</script>

<template>
  <div class="red">
    <h1>Count : {{ props.countView }}</h1>
  </div>
</template>


