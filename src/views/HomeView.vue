<script setup lang="ts">
import { reactive } from 'vue'
import { vMaska } from 'maska'

import InputText from '@/components/InputText.vue'

const phoneValue = reactive({
  masked: '',
  unmasked: '',
  completed: false
})
const phoneMask = reactive({
  mask: ['(##) ####-####', '(##) #####-####'],
  eager: true
})
</script>

<template>
  <section class="home section">
    <div class="home__presentation">
      <h2 class="home__title">Quer crescer o seu negócio?</h2>
      <p class="home__description">Maximize seus resultados com a Trek Digital!</p>
      <p class="home__description">
        Nossa equipe de especialistas em Google Ads e Meta Ads utiliza análise de dados para
        impulsionar sua marca. Comece a aumentar seus agendamentos hoje mesmo.
      </p>
      <p class="home__description">
        Entre em contato e descubra como nossas estratégias podem ajudá-lo a atingir seus objetivos!
      </p>
      <button class="button button--primary home__more-info">Quero mais informações</button>
    </div>
    <div class="home__lead">
      <form class="home__form" action="">
        <InputText placeholder="Seu nome" :required="true" class="home__input" />
        <InputText
          v-maska:[phoneMask]="phoneValue"
          placeholder="Seu Telefone"
          :required="true"
          class="home__input"
        />
        <InputText placeholder="Nome da empresa" :required="false" class="home__input" />
        <InputText placeholder="Site da empresa" :required="false" class="home__input" />
        <button type="submit" class="button button--primary home__more-info">
          Quero mais informações!
        </button>
      </form>
    </div>
  </section>
</template>
<style lang="scss" scoped>
@import '../assets/_variables';

.home {
  align-items: center;
  background: url(../assets/mountains.jpg);
  background-size: cover;
  box-shadow: inset 0 0 0 50vw #000000ad;
  display: flex;
  gap: 16px;
  justify-content: space-evenly;
  flex-wrap: wrap;
  min-height: calc(100vh - $contact-bar-height);
  padding: $header-height 16px;

  &__presentation {
    display: flex;
    flex-direction: column;
    width: 390px;
  }

  &__lead {
    max-width: 390px;
    width: 100%;
  }

  &__title {
    font-size: 28px;
    margin-bottom: 24px;
  }

  &__description {
    margin-bottom: 8px;
  }

  &__more-info {
    margin-top: 24px;
    width: 100%;
  }

  &__form {
    background-color: white;
    border-radius: 4px;
    padding: 16px;
  }

  &__input {
    display: block;
    width: 100%;
    margin-bottom: 4px;
  }
}
</style>
