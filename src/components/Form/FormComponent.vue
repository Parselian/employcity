<template>
  <form class="form" v-bind="$attrs" @submit="handleForm($event)">
    <div class="form__inputs">
      <SelectComponent :items="systemsList" class="form__select" v-model="system" name="user_system" placeholder="Выберите тип системы:"/>

      <InputComponent id="orders-form-email" class="form__input form__input-email" type="email" name="client_email"
                      placeholder="Ваш e-mail" v-model="email" required/>

      <InputComponent id="orders-form-name" class="form__input form__input-name" type="text" name="client_name"
                      placeholder="Ваше имя" v-model="name"/>


      <RangeComponent class="form__range" labelText="Sed ut perspiciatis, unde omnis iste natus" name="user_percent" hasPercent min=0
                      max=100 v-model="percent"/>

      <InputFile class="form__file" v-model="file" name="user_file"/>
    </div>

    <ButtonComponent class="form__submit" type="primary" text="Отправить"/>
  </form>
</template>

<script>
import './form.scss'
import axios from 'axios'

import SelectComponent from "@/components/ui/Select/SelectComponent"
import InputComponent from "@/components/ui/Input/InputComponent"
import RangeComponent from "@/components/ui/Range/RangeComponent"
import InputFile from "@/components/ui/InputFile/InputFile"
import ButtonComponent from "@/components/ui/Button/ButtonComponent"

export default {
  name: "FormComponent",
  data() {
    return {
      system: '',
      email: '',
      name: '',
      file: '',
      percent: 0,
      systemsList: ['Sed ut perspiciatis', 'Nemo enim ipsam', 'Et harum quidem', 'Temporibus autem', 'Itaque earum rerum', 'Et harum quidem', 'Temporibus autem', 'Itaque earum rerum', 'Itaque earum rerum'],
      reg: /^(([^<>()\\[\]\\.,;:\s@"]+(\.[^<>()\\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/
    }
  },
  methods: {
    isEmailValid: function() {
      return (this.email === "")? "" : (this.reg.test(this.email));
    },
    handleForm(event) {
      event.preventDefault()
      if (!this.isEmailValid()) {
        alert('Введите правильный E-mail!')
        return
      }

      let formData = new FormData();
      formData.append('system', this.system)
      formData.append('email', this.email)
      formData.append('name', this.name)
      formData.append('percent', this.percent)
      formData.append('file', this.file)


      axios.post('https://jsonplaceholder.typicode.com/posts', {
        data: formData,
        headers: {
          'Content-Type': 'multipart/form-data',
          'Access-Control-Allow-Origin': '*',
          'Accept': 'application/json'
        }
      })
          .then(() => {
            alert('SUCCESS')
          })
          .catch(() => {
            alert('ERROR')
          })
    }
  },
  components: {
    RangeComponent,
    SelectComponent,
    InputComponent,
    InputFile,
    ButtonComponent
  }
}
</script>

<style scoped>

</style>