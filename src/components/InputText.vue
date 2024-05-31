<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  placeholder: string
  required: boolean
}>()

const optionalLabel = computed(() => (!props.required ? ' (opcional)' : ''))
</script>
<template>
  <input type="text" :placeholder="placeholder + optionalLabel" class="input" />
</template>
<style lang="scss" scoped>
.input {
  border: 1px solid;
  border-radius: 4px;
  height: 50px;
  padding: 8px;

  &:focus-visible,
  &:active,
  &:focus {
    border: 2px solid;
    outline: none;
  }
}
</style>
