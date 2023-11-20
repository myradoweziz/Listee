<script setup>
import ButtonAll from './base/ButtonAll.vue'
</script>

<template>
  <section class="best-form">
    <div class="best-form__container">
      <div class="best-form__row">
        <div class="best-form__image">
          <img src="../assets/img/best_photo.png" alt="" />
        </div>
        <div class="best-form__back"></div>
        <div class="best-form__content">
          <div class="best-form__title">
            Get The Best Deals From <br />
            Our Listings In this Summer <br />
            <span> 20% Offer </span>
          </div>
          <ButtonAll title="Explore Now" />
        </div>
        <div class="best-form__cards">
          <img src="../assets/img/cards.png" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.best-form {
  position: relative;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 0 10px;
  }
  &__row {
    display: flex;
    justify-content: space-between;
    @media (max-width: 1180px) {
      flex-wrap: wrap;
      justify-content: space-around;
    }
  }
  &__image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    img {
      height: 100%;
      width: 100%;
      object-fit: cover;
      object-position: center;
    }
  }
  &__back {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
  }
  &__content {
    padding-top: 200px;
    padding-left: 20px;
    @media (max-width: 1180px) {
      padding-top: 100px;
    }
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 48px;
    line-height: 60px;
    color: #ffffff;
    padding-bottom: 20px;
    span {
      color: #ff823a;
    }
    @media (max-width: 768px) {
      font-size: 40px;
      br {
        display: none;
      }
    }
    @media (max-width: 425px) {
      font-size: 28px;
      line-height: 50px;
    }
  }
  &__cards {
    position: relative;
    padding-top: 70px;
    padding-right: 50px;
    @media (max-width: 768px) {
      padding-top: 0;
      width: 100%;
      padding-right: 0;
      img {
        width: 100%;
      }
    }

    &::before {
      content: '';
      position: absolute;
      bottom: 25px;
      left: -25%;
      width: 18%;
      height: 25%;
      background-image: url(../assets/img/spring.png);
      @media (max-width: 1180px) {
        left: -10px;
      }
    }
    &::after {
      content: '';
      position: absolute;
      top: 130px;
      right: -30px;
      width: 20%;
      height: 15%;
      background-image: url(../assets/img/half.png);
      @media (max-width: 768.99px) {
        top: 87px;
        right: -40px;
      }
    }
  }
}
</style>
