<script setup>
import Button from "@/components/Button.vue";
import Container from "@/components/Container.vue";
</script>

<template>
  <div class="banner">
    <Container>
      <div class="banner__info">
        <div class="banner__title">
          Уникальный подарок на <i>Новый&nbsp;год</i> -
          заезд за рулем спорктара по&nbsp;гоночной&nbsp;трассе
        </div>
        <div class="banner__sub-title">
          Подарите себе или близкому человеку яркие
          эмоции от езды без ограничений скорости!
        </div>
        <Button>Приобрести сертификат</Button>
      </div>
      <div class="banner__view">
        <img src="/banner.png" alt="">
      </div>
    </Container>
  </div>
</template>

<style lang="scss" scoped>
.banner {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;

  .container {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__info {
    width: 60%;
    max-width: 820px;

    i {
      color: #BF2920;
      font-style: normal;
    }

    .button {
      height: 72px;
      padding: 0 6.5%;
    }

    &:deep(.button__text) {
      font-weight: 600;
      font-size: 20px;
      line-height: 1.2;
    }
  }

  &__title {
    margin-bottom: 40px;
    font-size: 36px;
    line-height: 1.6;
    font-weight: 700;
    letter-spacing: 0.03em;
    text-transform: uppercase;
  }

  &__sub-title {
    width: 100%;
    max-width: 460px;
    margin-bottom: 60px;
    font-size: 20px;
    line-height: 1.6;
    font-weight: 400;
  }

  &__view {
    width: 100%;
    max-width: 65%;
    position: absolute;
    top: 20%;
    right: -8.5%;
    z-index: 0;

    img {
      width: 100%;
      max-width: 980px;
    }
  }
}

@media (max-width: 1279px) {
  .banner {
    &__info {
      width: 80%;
      &__title {
        font-size: 28px;
        line-height: 1.6;
        font-weight: 700;
      }
      &__sub-title {
        font-size: 20px;
        line-height: 1.6;
        font-weight: 400;
      }
      &:deep(.button__text) {
        font-size: 20px;
        line-height: 1.2;
        font-weight: 600;
      }
    }
    &__view {
      top: 45%;
      right: -5%;
    }
  }
}
@media (max-width: 1079px) {
  .banner {
    .container {
      display: flex;
      flex-direction: column;
    }

    &__info {
      width: 100%;
      max-width: 100%;
      padding-top: 6%;
    }

    &__title {
      margin-bottom: 20px;

      font-size: 24px;
      line-height: 1.6;
      font-weight: 700;
    }

    &__sub-title {
      margin-bottom: 40px;

      font-size: 18px;
      line-height: 1.6;
      font-weight: 400;
    }

    &__view {
      width: 100%;
      max-width: 560px;
      position: relative;
      top: 45px;
      left: 0;
      right: 0;
    }

  }
}
@media (max-width: 639px) {
  .banner {
    min-height: 0;
    align-items: flex-start;
    &__info {
      padding-top: 42%;
    }
    &__title {
      font-size: 18px;
      line-height: 1.6;
      font-weight: 700;
    }
    &__sub-title {
      font-size: 13px;
      line-height: 1.6;
      font-weight: 400;
    }
    .button {
      width: 100%;
      height: 60px;
      &:deep(.button__text) {
        font-size: 16px;
        line-height: 1.2;
        font-weight: 600;
      }
    }
    &__view {
      width: 110%;
      top: 20px;
      left: 0;
      right: 0;
    }
  }
}
</style>