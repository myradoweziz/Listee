<script setup>
import TitleAll from './base/TitleAll.vue'
import { reactive } from 'vue'
const categories = reactive([
  {
    title: 'Business',
    listing: '32 Listings'
  },
  {
    title: 'Education',
    listing: '47 Listings'
  },
  {
    title: 'Healthcare',
    listing: '74 Listings'
  },
  {
    title: 'Eat & Foods',
    listing: '68 Listings'
  }
])
</script>

<template>
  <section class="category">
    <div class="category__container">
      <header class="category__header header-category">
        <TitleAll title="Top Categories" />
        <div class="header-category__desc">
          Morbi mollis vestibulum sollicitudin. Nunc in eros a justo facilisis rutrum. Aenean id ullamcorper <br />
          libero Vestibulum imperdiet nibh vel magna lacinia commodo ultricies,
        </div>
      </header>
      <div class="category__products">
        <div class="category__row">
          <div v-for="item in categories" :key="item.title" class="category__body">
            <div class="category__image">
              <img src="../assets/img/business.png" alt="" />
            </div>
            <div class="category__content">
              <div class="category__title">{{ item.title }}</div>
              <div class="category__listings">{{ item.listing }}</div>
            </div>
            <div class="category__back"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.category {
  padding-bottom: 100px;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__header {
  }
  &__products {
  }
  &__row {
    display: flex;
    justify-content: space-around;
    gap: 50px;
    flex-wrap: wrap;
  }
  &__body {
    position: relative;
  }
  &__back {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, rgba(9, 21, 61, 0) 0%, #09153d 120.47%);
    box-shadow: 0px 30px 70px rgba(2, 13, 46, 0.04);
    border-radius: 20px;
  }
  &__content {
    position: absolute;
    bottom: 34px;
    left: 24px;
    z-index: 2;
  }
  &__image {
    width: 300px;
    height: 320px;
    img {
      max-width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center;
    }
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 30px;
    color: #ffffff;
  }
  &__listings {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 28px;
    color: #ffffff;
    padding: 6px 33px;
    background: rgba(255, 255, 255, 0.4);
    backdrop-filter: blur(15px);
    border-radius: 40px;
  }
}
.header-category {
  text-align: center;
  padding-bottom: 50px;
  &__desc {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 30px;
    color: #676c7b;
  }
}
</style>
