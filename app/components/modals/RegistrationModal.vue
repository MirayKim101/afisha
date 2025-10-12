<template>

  <div class="modal"  v-if="isVisibleModal">
    <div class="modal__shadow">
      <div class="modal__wrapper">
        <div class="modal__content">
          <div class="modal__content-heading">
            <slot name="heading"></slot>
          </div>
          <div class="modal__content-inner">
            <div class="modal__content-inner-fields">
              <InputField
                  v-model="registrationForm.name"
                  name="name" type="text"
                  placeholder="Имя"/>
              <InputField
                  v-model="registrationForm.lastName"
                  name="lastName" type="text"
                  placeholder="Фамилия"/>
              <InputField
                  v-model="registrationForm.email"
                  name="email" type="email"
                  placeholder="Email"/>
              <InputField
                  v-model="registrationForm.phone"
                  name="phone" type="text"
                  placeholder="Телефон"/>
              <InputField
                  v-model="registrationForm.password"
                  name="password" type="password"
                  placeholder="Пароль"/>
              <InputField
                  v-model="registrationForm.password_confirmation"
                  name="password_confirmation" type="password"
                  placeholder="Подтверждение пароля"/>
              <InputField
                  v-model="registrationForm.city"
                  name="city" type="text"
                  placeholder="Город"/>
            </div>

            <div class="modal__content-inner-btn">
              <button>
                Зарегистрироваться
              </button>
              <p>
                «Нажимая на кнопку, вы даете согласие на обработку персональных данных и соглашаетесь c политикой
                конфиденциальности»
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="modal__shadow">
    <div class="modal__content">
      <div class="modal__content-heading">

      </div>
    </div>
  </div>
</template>

<script setup>
import InputField from "~/components/ui/InputField.vue";

const props = defineProps({
  isVisibleModal: Boolean
})

const registrationForm = ref({
  name: null,
  lastName: null,
  email: null,
  phone: null,
  password: null,
  password_confirmation: null,
  city: 'novosibirks',

})


const emit = defineEmits(['close'])

const closeModal = () => {
  emit('close')
}
</script>

<style lang="scss" scoped>

</style>