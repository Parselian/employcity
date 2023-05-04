<template>
  <template v-if="type === 'h1'">
      <h1 v-bind="$attrs" v-html="text"></h1>
  </template>
  <template v-else-if="type === 'h2'">
      <h2 v-bind="$attrs" v-html="text"></h2>
  </template>
  <template v-else-if="type === 'h3'">
      <h3 v-bind="$attrs" v-html="text"></h3>
  </template>
  <template v-else-if="type === 'h4'">
      <h4 v-bind="$attrs" v-html="text"></h4>
  </template>
  <template v-else-if="type === 'h5'">
      <h5 v-bind="$attrs" v-html="text"></h5>
  </template>
  <template v-else-if="type === 'h6'">
      <h6 v-bind="$attrs" v-html="text"></h6>
  </template>
  <template v-else>
    <div>INCORRECT TITLE TYPE</div>
  </template>
</template>

<script>
import './title.scss'
export default {
  props: {
    type: 'h1' || 'h2' || 'h3' || 'h4' || 'h5' || 'h6',
    text: String,
  },
  name: "TitleComponent"
}
</script>

<style scoped>

</style>