<script setup>
import Container from "@/components/Container.vue";
</script>

<template>
  <Container class="benefits">
    <div class="benefits__title">
      В чем преимущества такого подарка?
    </div>
    <div class="benefit benefit_info-view">
      <div class="benefit__info">
        <div class="benefit__list">
          <div class="benefit__item">
            <div class="benefit__item-number">1</div>
            <div class="benefit__item-text">
              Подарок, который <i>будут помнить</i>, эмоции <i>на всю жизнь</i>
            </div>
          </div>
          <div class="benefit__item">
            <div class="benefit__item-number">2</div>
            <div class="benefit__item-text">
              <i>Эксклюзивные</i> спорткары, включая Porsche 911 GT3, Lamborghini Huracan STO и Ferrari F430
            </div>
          </div>
          <div class="benefit__item">
            <div class="benefit__item-number">3</div>
            <div class="benefit__item-text">
              Заезды проходят на профессиональных <i>гоночных треках:</i>
            </div>
          </div>
        </div>
      </div>
      <div class="benefit__view">
        <div class="benefit__tracks">
          <div class="benefit__track">
            <div class="benefit__track-title">
              Sochi Autodrom
            </div>
            <div class="benefit__track-view">
              <img src="/track-1.svg" alt="">
            </div>
            <div class="benefit__track-info">
              Активировать сертификат можно <i>до&nbsp;конца&nbsp;апреля&nbsp;2023*</i>
            </div>
          </div>
          <div class="benefit__track">
            <div class="benefit__track-title">
              Moscow Raceway
            </div>
            <div class="benefit__track-view">
              <img src="/track-2.svg" alt="">
            </div>
            <div class="benefit__track-info">
              Активировать сертификат можно <i>начиная&nbsp;с&nbsp;мая&nbsp;2023*</i>
            </div>
          </div>
        </div>
        <div class="benefit__view-description">*Актуальную информацию уточняйте у менеджера</div>
      </div>
    </div>
    <div class="benefit benefit_view-info">
      <div class="benefit__view">
        <img src="/gift.png" alt="">
        <div class="benefit__view-description">*Рекламные изображения могут отличаться от реальных продуктов</div>
      </div>
      <div class="benefit__info">
        <div class="benefit__list">
          <div class="benefit__item">
            <div class="benefit__item-number">4</div>
            <div class="benefit__item-text">
              <i>Вы</i> за рулем или на пассажирском сидении
            </div>
          </div>
          <div class="benefit__item">
            <div class="benefit__item-number">5</div>
            <div class="benefit__item-text">
              Для заезда на спорткаре вообще <i>не нужен стаж и опыт</i>, только наличие прав
            </div>
          </div>
          <div class="benefit__item">
            <div class="benefit__item-number">6</div>
            <div class="benefit__item-text">
            Мы даем возможность ехать <i>без ограничений скорости</i>, а чтобы вы комфортнее чувствовали себя, рядом будет
            профессиональный гонщик, который даст советы
            </div>
          </div>
        </div>
      </div>
    </div>
  </Container>
</template>

<style lang="scss" scoped>
.benefits {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;

  &__title {
    width: 100%;
    margin-bottom: 60px;

    text-align: left;
    font-size: 42px;
    line-height: 1.2;
    font-weight: 700;
  }
}

.benefit {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 -20px 40px;

  &__info {
    width: 100%;
    min-width: 50%;
    padding: 0 20px;
  }

  &__list {

  }

  &__item {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 40px 0;
    font-weight: 400;
    font-size: 22px;
    line-height: 1.4;

    &-number {
      width: 40px;
      min-width: 40px;
      position: relative;
      margin-right: 92px;
      text-align: center;
      font-size: 38px;
      line-height: 1.6;
      font-weight: 700;
      &:after {
        content: '';
        display: block;
        width: 52px;
        height: 1px;
        position: absolute;
        right: -72px;
        top: 50%;

        background-color: #ffffff;
      }
    }

    i {
      font-style: normal;
      color: #DC1C11;
    }

    & + .benefit__item {
      border-top: 1px solid #646464;
    }
  }

  &__view {
    width: 100%;
    min-width: 50%;
    padding: 0 20px;
    img {
      display: block;
      width: 100%;
      max-width: 100%;
    }
    &-description {
      margin-top: 8px;
      text-align: center;

      font-size: 16px;
      line-height: 1.3;
      font-weight: 400;
    }
  }

  &__tracks {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
  }

  &__track {
    width: 50%;
    padding: 20px 10px;
    border-radius: 20px;
    border: 1px solid #222222;
    background: linear-gradient(180deg, #1C1C1C 0%, rgba(28, 28, 28, 0) 100%);

    &-title {
      margin-bottom: 16px;
      text-align: center;
      font-size: 24px;
      line-height: 1.2;
      font-weight: 700;
    }

    &-view {
      margin-bottom: 12px;
      img {
        display: block;
        width: 100%;
        max-width: 100%;
      }
    }

    &-info {
      text-align: center;
      font-size: 16px;
      line-height: 1.3;
      font-weight: 400;
      i {
        font-style: normal;
        color: #DC1C11;
      }
    }

    & + .benefit__track {
      margin-left: 40px;
    }
  }
}
@media (max-width: 1279px) {
  .benefits {
    &__title {
      margin-bottom: 40px;

      font-size: 32px;
      line-height: 1.2;
      font-weight: 700;
    }
  }
  .benefit {
    margin: 0 -10px 20px;
    &__info {
      padding: 0 10px;
    }
    &__item {
      font-size: 18px;
      line-height: 1.4;
      &-number {
        font-size: 32px;
        line-height: 1.6;
        font-weight: 700;
        &:after {
          width: 42px;
          right: -62px;
        }
      }
    }
    &__track {
      padding: 34px 10px;
      & + .benefit__track {
        margin-left: 20px;
      }
    }

    &__view {
      padding: 0 10px;
    }
  }
}
@media (max-width: 1079px) {
  .benefits {
    margin-top: -10%;
    &__title {
      margin-bottom: 0;
      font-size: 28px;
      line-height: 1.2;
      font-weight: 700;
    }
  }
  .benefit {
    flex-direction: column;
    &__view > img {
      width: 85%;
      margin: 0 auto;
    }
    &_view-info {
      flex-direction: column-reverse;
    }
    &__track {
      &-title {
        font-size: 22px;
        line-height: 1.2;
        font-weight: 700;
      }
      &-view {
        width: 80%;
        margin: 0 auto 18px;
      }
    }
  }
}
@media (max-width: 639px) {
  .benefits {
    margin-top: 50px;
    &__title {
      margin-bottom: 12px;

      font-size: 20px;
      line-height: 1.2;
      font-weight: 700;
    }
  }
  .benefit {
    margin: 0;
    &__info {
      padding: 0;
      margin-bottom: 12px;
    }
    &__item {
      padding: 20px 0;
      &-number {
        min-width: 20px;
        margin-right: 56px;
        font-size: 20px;
        line-height: 1.6;
        font-weight: 700;
        &:after {
          width: 32px;
          right: -44px;
        }
      }
      &-text {
        font-size: 14px;
        line-height: 1.4;
        font-weight: 400;
      }
    }
    &__tracks {
      flex-direction: column;
    }
    &__track {
      width: 100%;
      padding: 25px 10px;
      &-title {
        font-size: 20px;
        line-height: 1.2;
        font-weight: 700;
      }

      &-info {
        font-size: 13px;
        line-height: 1.3;
        font-weight: 400;
      }

      & + .benefit__track {
        margin-top: 20px;
        margin-left: 0;
      }
    }
    &__view {
      padding: 0;
      margin-bottom: 12px;
      &-description {
        font-size: 11px;
        line-height: 1.3;
        font-weight: 400;
      }
    }
  }
}
</style>