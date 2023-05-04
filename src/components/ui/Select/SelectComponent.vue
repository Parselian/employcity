<template>
  <div class="select" :class="{'select_unrolled': this.isOpened}" v-on:click="toggleSelect">
    <input :id="id" type="text" :value="modelValue" :name="name" hidden>
    <div class="select__box">
      <div class="select__box-val">{{modelValue !== '' ? modelValue : placeholder}}</div>
      <img src="../../../assets/arrow.svg" alt="loremipsum.net" class="select__box-icon"/>
    </div>
    <ul class="select__dropdown">
      <li class="select__dropdown-item" v-for="item in items" :key="item" v-on:click="selectOption($event.target.textContent)">{{item}}</li>
    </ul>
  </div>
</template>

<script>
import './select.scss'
export default {
  name: "InputComponent",
  data() {
    return {
      isOpened: false
    }
  },
  props: {
    placeholder: String,
    items: Array,
    name: String,
    id: String,
    modelValue: String
  },
  methods: {
    toggleSelect: function () {
      this.isOpened = !this.isOpened
    },
    selectOption: function(val) {
      this.$emit('update:modelValue', val)
    }
  }
}
</script>

<style scoped>

</style>