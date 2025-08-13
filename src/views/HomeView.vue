<script setup>
import TheWelcome from '../components/TheWelcome.vue'

const count = ref(0);

</script>

<template>
  <main>
    <TheWelcome :countView="count"/>
  </main>
</template>
