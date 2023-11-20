<script setup>
import ButtonAll from './base/ButtonAll.vue'
import BaseIcon from './BaseIcon.vue'
import { reactive } from 'vue'
const locations = reactive([
  {
    icon: 'textFile',
    subTitle: 'Categories',
    subIcon: 'arrowBottom',
    title: 'Choose Category'
  },
  {
    icon: 'location',
    subTitle: 'Location',
    subIcon: 'arrowBottom',
    title: 'Liyakota, Indonesia'
  },
  {
    icon: 'card',
    subTitle: 'Pricing',
    subIcon: 'arrowBottom',
    title: 'Choose your budget'
  }
])
</script>

<template>
  <section class="explore">
    <div class="explore__container">
      <div class="explore__box">
        <div class="explore__content">
          <div class="explore__row">
            <div v-for="item in locations" :key="item.icon" class="explore__body">
              <div class="explore__icon">
                <BaseIcon :name="item.icon" />
              </div>
              <div class="explore__sub-content">
                <div class="explore__sub-title">
                  {{ item.subTitle }}
                  <BaseIcon :name="item.subIcon" />
                </div>
                <div class="explore__title">{{ item.title }}</div>
              </div>
            </div>
          </div>
          <div class="explore__btn">
            <ButtonAll title="Explore from Listings" icon="search" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.explore {
  padding-bottom: 100px;
  margin-top: -120px;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__box {
    background: rgba(255, 255, 255, 0.3);
    box-shadow: 0px 30px 70px rgba(2, 13, 46, 0.04);
    border-radius: 20px;
    padding: 30px;
    @media (max-width: 425px) {
      padding: 15px;
    }
  }
  &__content {
    padding: 45px 50px;
    background: #ffffff;
    box-shadow: 0px 30px 70px rgba(2, 13, 46, 0.04);
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    @media (max-width: 1280px) {
      gap: 10px;
      flex-wrap: wrap;
      justify-content: center;
    }
  }
  &__row {
    width: 78%;
    display: flex;
    justify-content: space-between;
    @media (max-width: 1280px) {
      width: 100%;
      flex-wrap: wrap;
      gap: 10px;
    }
    @media (max-width: 768px) {
      justify-content: center;
      flex-direction: column;
      gap: 30px;
      padding-bottom: 10px;
    }
  }
  &__body {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  &__sub-content {
  }

  &__icon {
    @media (max-width: 1024px) {
      width: 42px;
    }
  }
  &__sub-title {
    display: flex;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 14px;
    color: #676c7b;
    padding-bottom: 5px;
    span {
      color: #ee1c47;
    }
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 16px;
    color: #09153d;
    @media (max-width: 1024px) {
      font-size: 12px;
    }
  }
}
</style>
