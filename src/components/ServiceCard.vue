<script setup lang="ts">
const props = defineProps<{
  title: string
  description: string
}>()
</script>
<template>
  <article class="card">
    <div class="card__img">
      <slot />
    </div>
    <h3 class="card__title">{{ title }}</h3>
    <p class="card__description">{{ description }}</p>
  </article>
</template>
<style lang="scss" scoped>
.card {
  align-items: center;
  border: 1px solid white;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 10px;
  width: 225px;

  &__img {
    width: 50px;
  }

  &__description {
  }
}
</style>
