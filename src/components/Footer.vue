<script setup>
  import Container from "@/components/Container.vue";
  import Button from "@/components/Button.vue";
  import IconArror from "@/components/icons/IconArror.vue";
</script>

<template>
  <div class="footer">
    <Container>
      <div class="footer__row">
        <div class="footer__col">
          <div class="footer__title">Контакты</div>
        </div>
      </div>
      <div class="footer__row footer__contacts">
        <div class="footer__contact">
          <div class="footer__contact-title">Адрес</div>
          <div class="footer__contact-description">
            143650,&nbsp;Московская&nbsp;область
            <br />Волоколамский&nbsp;административный&nbsp;округ
            <br />Дер.&nbsp;Шелудьково,&nbsp;39
          </div>
        </div>
        <div class="footer__contact">
          <div class="footer__contact-title">Телефон</div>
          <div class="footer__contact-description"><a href="tel:84954453249">8 (495) 445-32-49</a></div>
        </div>
      </div>
      <div class="footer__row">
        <div class="footer__logo">SPORA GT</div>
        <Button class="button" href="https://sporagt.ru/"
        >На главный сайт <IconArror /></Button>
      </div>
    </Container>
  </div>
</template>

<style lang="scss" scoped>
.footer {
  padding-top: 80px;
  padding-bottom: 40px;
  margin-top: auto;
  margin-bottom: 0;
  background-color: #1c1c1c;
  &__title {
    margin-bottom: 40px;

    font-size: 28px;
    line-height: 1.2;
    font-weight: 700;
    color: #FFFFFF;
  }

  &__row {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  &__contacts {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    justify-content: space-between;

    margin-bottom: 80px;
  }

  &__contact {
    width: 100%;
    border-top: 1px solid #646464;
    padding-top: 24px;
    &-title {
      margin-bottom: 24px;

      font-size: 20px;
      font-weight: 600;
      line-height: 1.2;
    }
    &-description {
      font-size: 18px;
      line-height: 1.2;
      font-weight: 400;
      text-decoration: none;
      a {
        text-decoration: none;
      }
    }

    & + .footer__contact {
      margin-left: 60px;
    }
  }

  &__logo {
    font-size: 24px;
    line-height: 1.2;
    font-weight: 700;
    color: #BF2920;
  }
}
@media (max-width: 1279px) {
  .footer {
    padding-top: 60px;
    &__title {
      margin-bottom: 20px;

      font-size: 24px;
      line-height: 1.2;
      font-weight: 600;
    }
    &__contacts {
      flex-direction: column;
      align-items: flex-start;
      justify-content: flex-start;
      margin-bottom: 60px;
    }
    &__contact {
      margin-left: 0;
      & + .footer__contact {
        margin-top: 60px;
        margin-left: 0;
      }
    }
  }
}
@media (max-width: 1079px) {
  .footer {
    padding-top: 50px;
    padding-bottom: 20px;
    &__title {
      margin-bottom: 26px;

      font-size: 32px;
      line-height: 1.2;
      font-weight: 700;
    }
    &__contacts {
      margin-bottom: 50px;
    }
    &__contact {
      border-top: none;
      &-title {
        margin-bottom: 16px;
      }
      & + .footer__contact {
        margin-top: 0;
      }
    }
  }
}
@media (max-width: 639px) {
  .footer {
    padding-top: 40px;
    &__title {
      margin-bottom: 12px;
      font-size: 18px;
      line-height: 1.2;
      font-weight: 600;
    }
    &__contacts {
      margin-bottom: 40px
    }
    &__contact {
      padding-top: 20px;
      &-title {
        margin-bottom: 10px;
        font-size: 13px;
        line-height: 1.2;
        font-weight: 600;
      }
      &-description {
        font-size: 13px;
        line-height: 1.2;
        font-weight: 400;
      }
    }
    &__logo {
      font-size: 18px;
      line-height: 1.2;
      font-weight: 700;
    }
    .button {
      height: 36px;
      padding: 0 10px;
      &:deep(.button__text) {
        font-size: 13px;
        line-height: 1.2;
        font-weight: 500;
      }
    }
  }
}
</style>