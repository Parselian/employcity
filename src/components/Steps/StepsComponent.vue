<template>
  <div class="steps">
    <div class="step" v-for="step in steps" :key="step.text">
      <div class="step__icon-wrap">
        <img :src="require(`@/assets/${step.iconID}`)" alt="loremipsum.net" class="step__icon">
      </div>
      <div class="step__text">{{step.text}}</div>
    </div>
  </div>
</template>

<script>
import './steps.scss'
export default {
  name: "StepsComponent",
  props: {
    steps: Array
  }
}
</script>

<style scoped>

</style>