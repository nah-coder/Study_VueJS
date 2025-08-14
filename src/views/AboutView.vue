<script setup>
import { RouterView, useRouter } from 'vue-router'

const router = useRouter()
</script>


<template>
  <div class="about">
    <!-- <button @click="router.push({name:'user'})">redirert about view user</button> -->

    <RouterLink to="/about/user">redirert about view user</RouterLink>
    <h1>This is an about page</h1>
    <router-view></router-view>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
