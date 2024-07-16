<script setup lang="ts">
import ServiceCard from '@/components/ServiceCard.vue'
import GoogleAdsIcon from '@/components/icons/GoogleAdsIcon.vue'
import MetaAdsIcon from '@/components/icons/MetaAdsIcon.vue'
import PageIcon from '@/components/icons/PageIcon.vue'
import PageIcon2 from '@/components/icons/PageIcon2.vue'
import CallCenterIcon from '@/components/icons/CallCenterIcon.vue'
import PhoneIcon from '@/components/icons/PhoneIcon.vue'

const services = [
  {
    title: 'Google Ads',
    image: GoogleAdsIcon,
    description: ''
  },
  {
    title: 'Meta Ads',
    image: MetaAdsIcon,
    description: ''
  },
  {
    title: 'Páginas',
    image: PageIcon,
    description: ''
  },
  {
    title: 'Páginas2',
    image: PageIcon2,
    description: ''
  },
  {
    title: 'Treinamento para equipe de atendimento e vendas',
    image: CallCenterIcon,
    description: ''
  },
  {
    title: 'Rastreamento e monitoramento de suas ligações',
    image: PhoneIcon,
    description: ''
  }
]
</script>

<template>
  <section class="services section">
    <h2 class="services__title">
      Desenvolvemos estratégias de tráfego pago personalizadas para as necessidades específicas da
      sua empresa.
    </h2>
    <div class="services__content">
      <h2 class="services__content-title">Conheça os nossos serviços</h2>
      <div class="services__cards">
        <ServiceCard
          v-for="(item, index) in services"
          :key="index"
          :title="item.title"
          :description="item.description"
        >
          <component :is="item.image" />
        </ServiceCard>
      </div>
      <button class="button button--primary services__action">Solicitar orçamento</button>
    </div>
  </section>
</template>
<style lang="scss" scoped>
.services {
  background-color: white;
  color: black;
  text-align: center;
  align-items: center;
  display: flex;
  flex-direction: column;

  &__action {
    margin-top: 24px;
    width: 100%;
  }

  &__title {
    margin-bottom: 16px;
  }

  &__content {
    max-width: 600px;
  }

  &__content-title {
    margin-bottom: 16px;
  }

  &__cards {
    display: flex;
    gap: 10px;
    justify-content: space-evenly;
    flex-wrap: wrap;
  }
}
</style>
