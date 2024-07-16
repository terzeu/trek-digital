<script setup lang="ts">
import { ref } from 'vue'
import WppIcon from '@/components/icons/WppIcon.vue'
import EmailIcon from '@/components/icons/EmailIcon.vue'

const isSticked = ref<boolean>(false)

window.addEventListener('scroll', () => {
  if (window.scrollY > 40) {
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
    <div class="header__logo">
      <img src="../assets/imgs/logo-white-2.png" alt="" width="100" />
    </div>
    <div class="header__menu">
      <a class="header__menu-item" href="#">Início</a>
      <a class="header__menu-item" href="#services">Nossos Serviços</a>
      <a class="header__menu-item" href="#specialist">Fale com um especialista</a>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import '../assets/_variables';

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
    height: $contact-bar-height;
  }

  &__bar {
    align-items: center;
    background-color: transparent;
    color: white;
    display: flex;
    justify-content: space-between;
    height: $header-height;
    position: absolute;
    top: $contact-bar-height;
    transition: background-color 500ms ease;

    &--sticked {
      background-color: rgb($secondary, 0.8);
      border-bottom: 1px solid white;
      position: -webkit-sticky; /* Safari */
      position: fixed;
      top: 0;
    }
  }

  &__logo {
  }

  &__menu {
    align-items: center;
    display: flex;
    gap: 10px;
    justify-content: end;
    margin-left: 16px;
    width: 100%;
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
