<template>
  <input :class="['input', isEmailValid()]" v-bind="$attrs" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"/>
</template>

<script>
import './input.scss'

export default {
  name: "InputComponent",
  props: {
    'modelValue': String || Number,
    'type': String
  },
  data() {
    return {
      reg: /^(([^<>()\\[\]\\.,;:\s@"]+(\.[^<>()\\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/
    }
  },
  methods: {
    isEmailValid: function() {
      if (this.type !== 'email') return
      return (this.modelValue === "")? "" : (this.reg.test(this.modelValue)) ? 'input_success' : 'input_error';
    }
  }
}
</script>

<style scoped>

</style>