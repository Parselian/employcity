<template>
  <div class="file">
    <input id="input-file" type="file" :name="$attrs.name" hidden @change="$emit('update:modelValue', $event.target.value)">
    <label for="input-file" class="file__label">
      <img class="file__label-icon" src="../../../assets/form-document.svg" alt="loremipsum.net">
      <span class="file__label-text">
        {{
          modelValue !== ''
              ? `${modelValue.substring(modelValue.lastIndexOf('\\')+1).slice(0, 16)}...`
              : 'Прикрепить файл'
        }}
      </span>
    </label>
  </div>
</template>

<script>
import './file.scss'
export default {
  name: "InputFile",
  props: ['modelValue']
}
</script>

<style scoped>

</style>