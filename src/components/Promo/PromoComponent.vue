<template>
  <section class="promo">
    <img src="../../assets/promo__bg.jpg" alt="loremipsum.net" class="promo__bg">

    <div class="promo__wrap container">
      <TitleComponent type="h1" class="promo__title" :text="promoTitle"/>

      <div class="promo__content">
        <div class="promo__text">
          At vero eos et accusamus et iusto odio dignissimos ducimus!
        </div>

        <ul class="promo__list">
          <li class="promo__list-item">Totam rem aperiam eaque ipsa</li>
          <li class="promo__list-item">Sit voluptatem accusantium doloremque laudantium</li>
          <li class="promo__list-item">Sed ut perspiciatis, unde omnis iste natus error</li>
        </ul>

        <div class="promo__buttons">
          <ButtonComponent class="promo__button" type="primary" text="Заказать"/>
          <ButtonComponent class="promo__button" type="inverted" text="Подробнее"/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import './promo.scss'

import TitleComponent from "@/components/ui/Title/TitleComponent"
import ButtonComponent from "@/components/ui/Button/ButtonComponent"
export default {
  name: "PromoComponent",
  data() {
    return {
      promoTitle: '<span class="text-accent">Lorem</span> ipsum dolor sit <span class="line-break"></span> amet consectetur <span class="text-accent">adipiscing</span>'
    }
  },
  components: {
    TitleComponent,
    ButtonComponent
  }
}
</script>

<style scoped>

</style>