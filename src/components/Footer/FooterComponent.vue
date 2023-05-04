<template>
  <footer class="footer">
    <div class="footer__wrap container">
      <div class="footer__col footer__copyright">© 2018 «LoremIpsum.net» Все права защищены.</div>

      <div class="footer__col footer__links">
        <div class="footer__payments">
          <div class="footer__payment" v-for="payment in payments" :key="payment.text">
            <img :src="require(`@/assets/${payment.iconID}`)" alt="loremipsum.net" class="footer__payment-icon">
            <div class="footer__payment-text">{{ payment.text }}</div>
          </div>
        </div>

        <div class="footer__socials">
          <a :href="social.link" class="footer__social" v-for="social in socials" :key="social.text">
            <img :src="require(`@/assets/${social.iconID}`)" alt="loremipsum.net" class="footer__social-icon">
            <span class="footer__social-text">{{ social.text }}</span>
          </a>
        </div>
      </div>


    </div>
  </footer>
</template>

<script>
import './footer.scss'

export default {
  name: "FooterComponent",
  props: {
    payments: Array,
    socials: Array
  }
}
</script>

<style scoped>

</style>