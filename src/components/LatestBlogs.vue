<script setup>
import BaseIcon from './BaseIcon.vue'
import { reactive } from 'vue'
import ButtonAll from './base/ButtonAll.vue'
const educations = reactive([
  {
    title: '30 popular business listings of this pandemic year 2021',
    day: '24th Dec, 2021 .'
  },
  {
    title: 'Most visited places & top rated shops from our listing',
    day: '17th Oct, 2011 .'
  },
  {
    title: 'Optimize your business page for national/global customers',
    day: '10th , 2025.'
  }
])
</script>

<template>
  <section class="latest">
    <div class="latest__container">
      <div class="latest__title">
        Latest Blogs
        <BaseIcon name="line" />
      </div>
      <div class="latest__education-places education-places">
        <div v-for="item in educations" :key="item.title" class="education-places__body">
          <div class="education-places__image">
            <img src="../assets/img/person.png" alt="" />
          </div>
          <div class="education-places__content">
            <div class="education-places__title">{{ item.title }}</div>
            <div class="education-places__desc">
              You’ve probably noticed there are dozens of platforms that offer business listings. Let’s look at a few of
              the most popular sites and...
            </div>
            <div class="education-places__date">
              <span>{{ item.day }}</span>
              5 min read
            </div>
          </div>
        </div>
      </div>
      <div class="latest__btn">
        <ButtonAll title="View All" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.latest {
  padding-bottom: 100px;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 48px;
    line-height: 60px;
    text-align: center;
    color: #09153d;
    padding-bottom: 30px;
    span {
      margin-top: -15px;
      justify-content: center;
      :deep(svg) {
        z-index: -1;
      }
    }
  }
  &__education-places {
  }
  &__btn {
    display: flex;
    justify-content: center;
  }
}
.education-places {
  display: flex;
  justify-content: space-between;
  gap: 30px;
  padding-bottom: 50px;
  @media (max-width: 768px) {
    flex-wrap: wrap;
    justify-content: center;
  }
  &__body {
    width: 486px;
    background: #ffffff;
    box-shadow: 0px 30px 70px rgba(2, 13, 46, 0.04);
    border-radius: 24px;
  }
  &__image {
    img {
      width: 100%;
      height: 100%;
    }
  }
  &__content {
    padding: 24px;
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
    line-height: 30px;
    color: #676c7b;
    padding-bottom: 24px;
  }
  &__date {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 24px;
    color: #676c7b;
    span {
      color: #ff823a;
    }
  }
}
</style>
