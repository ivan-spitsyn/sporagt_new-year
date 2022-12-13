<script setup>
import Container from "@/components/Container.vue";
import Button from "@/components/Button.vue";
import { vMaska } from "maska"
import { useForm } from 'vee-validate';
import { ref } from "vue";

let formName = ref(''),
    formPhone = ref(''),
    validFormName = ref(true),
    validFormPhone = ref(true);


function sendForm(event) {
  validFormName.value = validateName(formName);
  validFormPhone.value = validatePhone(formPhone);

  if (!validFormName.value || !validFormPhone.value) {
    return;
  }

  fetch("https://sporagt.ru/api/", {
    method: "POST",
    headers: {
      "Content-type": "application/json; charset=UTF-8",
    },
    body: JSON.stringify({
      name: formName.value,
      phone: formPhone.value,
    }),
  })
  .then((response) => response.json())
  .then((json) => console.log(json));

}
function changeName(name) {
  formName.value = name;
  validFormName.value = validateName(name);
}
function changePhone(phone) {
  formPhone.value = phone;
  validFormPhone.value = validatePhone(phone);
}
function validateName(name) {

  return name.length > 1;
}
function validatePhone(phone) {
  return phone.length === 18;
}
</script>
<template>
  <Container class="request">
    <form method="post" class="form" action="">
      <div class="form__title">Оставьте заявку на сертификат - мы позвоним вам и обсудим детали</div>

      <div class="form__field form-field">
        <div class="form-field__label">Ваше Имя</div>
        <input
            :value="formName"
            @input="event => changeName(event.target.value)"
            :class="['form-field__input', { 'error': !validFormName }]"
            v-maska data-maska="A A A"
            data-maska-tokens="A:[a-zA-Zа-яА-Я]:multiple"
            placeholder="Имя"
            type="text"
            required
        >
      </div>

      <div class="form__field form-field">
        <div class="form-field__label">Ваш номер телефона</div>
        <input
            :value="formPhone"
            @input="event => changePhone(event.target.value)"
            :class="['form-field__input', { 'error': !validFormPhone }]"
            v-maska data-maska="+7 (###) ###-##-##"
            placeholder="+7"
            type="tel"
            required
        >
      </div>

      <div class="form__police">
        Нажимая кнопку "Подать заявку", Вы даете согласие на обработку персональных данных и
        соглашаетесь c <a href="https://sporagt.ru/privacy/" target="_blank">политикой конфиденциальности</a>
      </div>

      <Button @click.prevent="sendForm" >Оставить заявку</Button>
    </form>
    <div class="logo">
      <img src="/logo.svg" alt="">
    </div>
  </Container>
</template>
<style lang="scss" scoped>
.request {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.logo {
  img {
    display: block;
    width: 100%;
    max-width: 100%;
  }
}

.form {
  width: 100%;
  max-width: 710px;
  padding: 80px 0;
  &__title {
    margin-bottom: 24px;

    font-size: 36px;
    line-height: 1.2;
    font-weight: 700;
    color: #ffffff;
  }

  &__police {
    margin-bottom: 24px;

    font-size: 15px;
    line-height: 1.2;
    font-weight: 400;
  }

  .button {
    width: 100%;
    height: 92px;
    &:deep(.button__text) {
      font-size: 24px;
      line-height: 1.2;
      font-weight: 600;
    }
  }
}

.form-field {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  margin-bottom: 24px;

  &__label {
    margin-bottom: 8px;

    font-size: 18px;
    line-height: 1.2;
    font-weight: 400;
    color: #ffffff;
  }
  &__input {
    width: 100%;
    height: 72px;
    padding: 0 24px;
    border: 2px solid transparent;
    border-radius: 8px;
    background: #ffffff;
    outline: transparent;

    font-size: 24px;
    line-height: 1.2;
    font-weight: 400;
    &.error {
      border-color: #ff0000;
    }
  }
}

@media (max-width: 1279px) {
  .request {}
  .form {
    padding: 60px 0;
    max-width: 600px;
    &__title {
      font-size: 32px;
      line-height: 1.2;
      font-weight: 700;
    }
  }
  .logo {
    max-width: 348px;
  }
}
@media (max-width: 1079px) {
  .logo {
    display: none;
  }
  .form {
    padding: 106px 0 44px;
    &__title {
      font-size: 28px;
      line-height: 1.2;
      font-weight: 700;
    }
    .button {
      height: 80px;
    }
  }
}
@media (max-width: 639px) {
  .form {
    padding: 40px 0;
    &__title {
      font-size: 18px;
      line-height: 1.2;
      font-weight: 600;
    }
    .button {
      height: 60px;
      &:deep(.button__text) {
        font-size: 16px;
        line-height: 1.2;
        font-weight: 600;
      }
    }
  }
  .form-field {
    &__label {
      font-size: 13px;
      line-height: 1.2;
      font-weight: 400;
    }
    &__input {
      height: 56px;

      font-size: 18px;
      line-height: 1.2;
      font-weight: 400;
    }
  }
}
</style>