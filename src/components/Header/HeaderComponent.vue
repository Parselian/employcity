<template>
  <header class="header">
    <div class="header__wrap container">
      <div class="header__logo">
        Loremipsum.<span class="header__logo_accent">net</span>
      </div>
      <nav class="header__menu">
        <a href="#" class="header__menu-item header__menu-item_active">Бизнес</a>
        <a href="#" class="header__menu-item">О нас</a>
        <a href="#" class="header__menu-item">Цены</a>
        <a href="#" class="header__menu-item">Оформить заказ</a>
      </nav>
      <BurgerBtn class="header__burger"/>
    </div>
  </header>
</template>

<script>
import './header.scss'

import BurgerBtn from "@/components/ui/BurgerBtn/BurgerBtn"

export default {
  name: "HeaderComponent",
  components: {
    BurgerBtn
  }
}
</script>

<style scoped>

</style>