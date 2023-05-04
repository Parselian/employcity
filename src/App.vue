<template>
  <HeaderComponent/>
  <div class="main">
    <PromoComponent/>
    <OrdersComponent/>
  </div>
  <FooterComponent :payments="footerPaymentSystems" :socials="footerSocials"/>
</template>

<script>
import HeaderComponent from "@/components/Header/HeaderComponent"
import PromoComponent from "@/components/Promo/PromoComponent"
import OrdersComponent from "@/components/Orders/OrdersComponent"
import FooterComponent from "@/components/Footer/FooterComponent"

export default {
  name: 'App',
  data() {
    return {
      footerPaymentSystems: [
        {
          iconID: 'qiwi.svg',
          text: 'QIWI wallet'
        },
        {
          iconID: 'yandex-money.svg',
          text: 'Yandex Money'
        },
        {
          iconID: 'webmoney.svg',
          text: 'Web Money'
        },
      ],
      footerSocials: [
        {
          iconID: 'mail.svg',
          link: 'mailto:info@ipsum228.com',
          text: 'info@ipsum228.com'
        },
        {
          iconID: 'vk.svg',
          link: 'https://vk.com',
          text: 'Мы вконтакте'
        }
      ]
    }
  },
  components: {
    HeaderComponent,
    PromoComponent,
    OrdersComponent,
    FooterComponent
  }
}
</script>

<style>

</style>
