<template>
  <label for="check" class="burger-btn" v-bind="$attrs">
      <input class="burger-btn__input" type="checkbox" id="check" hidden/>
      <span></span>
      <span></span>
      <span></span>
    </label>
</template>

<script>
import './burger-btn.scss'
export default {
  name: "BurgerBtn"
}
</script>

<style scoped>

</style>