<script setup>
import BaseIcon from './BaseIcon.vue'
import { reactive } from 'vue'
const works = reactive([
  {
    icon: 'window',
    title: 'Choose Your Category',
    desc: 'Dolor sit amet consectetur adipisicing elit. Reprehenderit, illo ex esse...'
  },
  {
    icon: 'locationSearch',
    title: 'Find What You Want',
    desc: 'Dolor sit amet consectetur adipisicing elit. Reprehenderit, illo ex esse...'
  },
  {
    icon: 'compass',
    title: 'Explore Our Listings',
    desc: 'Dolor sit amet consectetur adipisicing elit. Reprehenderit, illo ex esse...'
  }
])
</script>

<template>
  <section class="work">
    <div class="work__container">
      <header class="work__header header-work">
        <div class="header-work__title">
          How It Works
          <BaseIcon name="line" />
        </div>
        <div class="header-work__desc">
          Morbi mollis vestibulum sollicitudin. Nunc in eros a justo facilisis rutrum. Aenean id ullamcorper <br />
          libero Vestibulum imperdiet nibh vel magna lacinia commodo ultricies,
        </div>
      </header>
      <div class="work__box">
        <div v-for="item in works" :key="item.icon" class="work__body">
          <div class="work__icon">
            <BaseIcon :name="item.icon" />
            <div class="work__content">
              <div class="work__title">{{ item.title }}</div>
              <div class="work__desc">{{ item.desc }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.work {
  padding-bottom: 100px;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__header {
  }
  &__box {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 30px;
    @media (max-width: 768px) {
      justify-content: center;
      flex-wrap: wrap;
    }
  }
  &__body {
    background: #ffffff;
    box-shadow: 0px 10px 70px rgba(2, 13, 46, 0.04);
    border-radius: 24px;
    padding: 40px;
    text-align: center;
  }
  &__icon {
    span {
      padding-bottom: 30px;
      justify-content: center;
    }
  }
  &__content {
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 30px;
    color: #09153d;
    padding-bottom: 8px;
  }
  &__desc {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 28px;
    color: #676c7b;
  }
}
.header-work {
  text-align: center;
  padding-bottom: 50px;
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 48px;
    line-height: 60px;
    color: #09153d;
    padding-bottom: 30px;
    span {
      margin-top: -15px;
      justify-content: center;
    }
  }
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
