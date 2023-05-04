<template>
  <button class="button" v-bind="$attrs" :class="{
    'button_primary': type === 'primary',
    'button_inverted': type === 'inverted'}">
    {{this.text}}
  </button>
</template>

<script>
import './button.scss'
export default {
  props: {
    type: 'primary' || 'inverted',
    text: String,
    iconId: String,
  },
  name: "ButtonComponent"
}
</script>

<style scoped>

</style>