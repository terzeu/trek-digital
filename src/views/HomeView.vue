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
      <p class="home__question">Quer crescer o seu negócio?</p>
      <h2 class="home__maximize">Maximize seus resultados com a Trek Digital!</h2>
      <p class="home__description">
        Nossa equipe de especialistas em Google Ads e Meta Ads utiliza análise de dados para
        impulsionar sua marca. Comece a aumentar seus agendamentos hoje mesmo.
      </p>
      <p class="home__description">
        Entre em contato e descubra como nossas estratégias podem ajudá-lo a atingir seus objetivos!
      </p>
      <button class="home__more-info">Quero mais informações</button>
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
        <button type="submit">Quero mais informações!</button>
      </form>
    </div>
  </section>
</template>
<style lang="scss" scoped>
.home {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;

  &__presentation {
    width: 50%;
    min-width: 300px;
  }

  &__lead {
    width: 50%;
    max-width: 390px;
  }

  &__question {
    font-size: 16px;
    margin-bottom: 4px;
  }

  &__maximize {
    font-size: 28px;
    margin-bottom: 12px;
  }

  &__description {
    margin-bottom: 8px;
  }

  &__more-info {
    margin-top: 24px;
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
