<template>
  <template v-if="hasPercent">
    <div class="range__wrap">
      <div class="range__label">{{labelText}}</div>
      <div class="range__data">{{modelValue}}%</div>
      <input class="range" type="range" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"
             v-bind="$attrs" :min=min :max=max />
    </div>
  </template>
  <template v-else>
    <input class="range" type="range" :value="modelValue" @input="$emit('update:modelValue', parseInt($event.target.value))"
           v-bind="$attrs"/>
  </template>
</template>

<script>
import './range.scss'
export default {
  name: "InputComponent",
  props: {
    modelValue: Number,
    labelText: String,
    hasPercent: Boolean,
    min: Number,
    max: Number
  }
}
</script>

<style scoped>

</style>