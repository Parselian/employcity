<template>
  <section class="orders">
    <div class="orders__wrap container">
      <TitleComponent type="h2" class="orders__title" :text="ordersTitle"/>
      <div class="orders__subtitle">Перед заполнением формы ознакомьтесь с нашей схемой работы!</div>
      <StepsComponent :steps="steps"/>
      <FormComponent class="orders__form"/>
    </div>
  </section>
</template>

<script>
import './orders.scss'

import TitleComponent from "@/components/ui/Title/TitleComponent"
import StepsComponent from "@/components/Steps/StepsComponent"
import FormComponent from "@/components/Form/FormComponent"

export default {
  name: "OrdersComponent",
  data() {
    return {
      ordersTitle: 'Оформление <span class="text-accent">Заказа</span>',
      steps: [
        {
          iconID: 'magnifier.svg',
          text: '1 Lorem ipsum dolor sit amet'
        },
        {
          iconID: 'magnifier.svg',
          text: '2 Lorem ipsum dolor sit amet'
        },
        {
          iconID: 'magnifier.svg',
          text: '3 Lorem ipsum dolor sit amet'
        },
        {
          iconID: 'magnifier.svg',
          text: '4 Lorem ipsum dolor sit amet'
        },
        {
          iconID: 'percent.svg',
          text: '5 Сonsecteturadipiscing elit'
        },

      ]
    }
  },
  components: {
    TitleComponent,
    StepsComponent,
    FormComponent
  }
}
</script>

<style scoped>

</style>