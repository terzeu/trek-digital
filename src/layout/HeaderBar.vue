<script setup lang="ts">
import { ref } from 'vue'
import WppIcon from '@/components/icons/WppIcon.vue'
import EmailIcon from '@/components/icons/EmailIcon.vue'

const isSticked = ref<boolean>(false)

window.addEventListener('scroll', () => {
  if (window.scrollY > 35) {
    isSticked.value = true
  } else {
    isSticked.value = false
  }
})
</script>

<template>
  <div class="header__contacts">
    <a class="contact" href="">
      <WppIcon class="contact__icon" width="14" height="14" />
      (61) 99699-3793
    </a>
    <a class="contact" href="">
      <EmailIcon class="contact__icon" width="14" height="14" />
      contato@agenciatrek.digital
    </a>
  </div>
  <nav :class="['header__bar', { 'header__bar--sticked': isSticked }]">
    <div class="header__logo"></div>
    <div class="header__menu">
      <a class="header__menu-item" href="#">Início</a>
      <a class="header__menu-item" href="#services">Nossos Serviços</a>
      <a class="header__menu-item" href="#specialist">Fale com um especialista</a>
    </div>
  </nav>
</template>

<style lang="scss">
.header {
  &__bar,
  &__contacts {
    width: 100%;
    padding: 20px;
  }

  &__contacts {
    align-items: center;
    background-color: white;
    color: black;
    display: flex;
    gap: 20px;
    height: 40px;
  }

  &__bar {
    align-items: center;
    background-color: transparent;
    color: white;
    display: flex;
    justify-content: space-between;
    height: var(--header-height);
    position: -webkit-sticky; /* Safari */
    position: sticky;
    top: 0;
    transition: background-color 500ms ease;

    &--sticked {
      background-color: #e05928;
    }
  }

  &__logo {
    background-color: blue;
    height: 50px;
    width: 50px;
  }

  &__menu {
    display: flex;
    gap: 10px;
  }

  &__menu-item {
    color: inherit;
  }
}

.contact {
  color: black;

  &__icon {
    margin-right: 4px;
  }
}
</style>
