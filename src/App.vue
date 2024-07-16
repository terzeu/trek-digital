<script setup lang="ts">
import { RouterView } from 'vue-router'
import HeaderBar from './layout/HeaderBar.vue'
</script>

<template>
  <HeaderBar />

  <main class="page">
    <RouterView />
    <RouterView id="services" name="services" />
    <RouterView id="specialist" name="specialist" />
  </main>
</template>

<style lang="scss" scoped>
.page {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
