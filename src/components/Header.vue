<script setup>
import Button from "./Button.vue";
import Container from "@/components/Container.vue";
import IconPhone from "@/components/icons/IconPhone.vue";

function showModal() {

}

</script>

<template>
  <header class="header">
    <Container>
      <div class="header__logo">
        <img src="/logo.svg" alt="">
      </div>
      <a href="tel:84954453249" class="header__phone">
        <IconPhone /> <span>8 (495) 445-32-49</span>
      </a>
      <div @click="showModal" class="header__callback callback">
        <div class="callback__phone">
          <div class="callback__phone-title">Заказать звонок</div>
          <a class="callback__phone-link" href="tel:84954453249"><IconPhone /> <span>8 (495) 445-32-49</span></a>
        </div>
        <Button class="callback__button">Обратный звонок</Button>
      </div>
    </Container>
  </header>
</template>

<style lang="scss" scoped>
.header {
  width: 100%;
  padding: 32px 0;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 9;
  .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__logo {
    max-width: 88px;
    margin-left: 0;
    margin-right: 40px;

    img {
      max-width: 100%;
    }
  }
  &__phone {
    position: relative;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    margin-left: 0;
    margin-right: auto;
    text-decoration: none;

    font-size: 20px;
    line-height: 1.2;
    font-weight: 400;

    svg {
      margin-right: 2px;
    }
    &:after {
      content: "";
      position: absolute;
      bottom: -4px;
      left: 0;
      display: block;
      width: 100%;
      border: 1px dashed #ffffff;
    }
  }
  &__callback {}
}
.callback {
  &__phone {
    display: none;
    flex-direction: column;
    align-items: center;
    &-title {
      margin-bottom: 12px;

      font-size: 14px;
      line-height: 1.2;
      font-weight: 500;
      color: #BF2920;
    }
    &-link {
      font-size: 12px;
      line-height: 1.2;
      font-weight: 400;
      text-decoration: none;

      svg {
        width: 15px;
        height: 15px;
        margin-right: 2px;
        margin-bottom: -5px;
      }
    }
  }
  .button {
    &:deep(.button__text) {
      font-size: 18px;
      line-height: 1.2;
      font-weight: 500;
    }
  }
}
@media (max-width: 1279px) {

}
@media (max-width: 1079px) {
  .header {
    &__logo {
      width: 68px;
    }
    &__phone {
      display: none;
    }
  }
  .callback {
    &__phone {
      display: flex;
    }
    .button {
      display: none;
    }
  }
}
@media (max-width: 639px) {
  .header {
    padding: 14px 0;
    &__logo {
      width: 48px;
    }
  }
  .callback {
    &__phone {
      align-items: flex-end;
      &-title {
        font-size: 13px;
        margin-bottom: 10px;
      }
      &-link {
        font-size: 11px;
      }
    }
  }
}
</style>