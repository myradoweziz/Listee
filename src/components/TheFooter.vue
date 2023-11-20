<script setup>
import BaseIcon from './BaseIcon.vue'
import { ref } from 'vue'
const icons = ref([
  {
    name: 'facebook'
  },
  {
    name: 'instagram'
  },
  {
    name: 'youtube'
  },
  {
    name: 'twitter'
  }
])
const categories = ref([
  {
    title: 'Popular Categories',
    care: 'Health care',
    business: 'Business',
    education: 'Education',
    food: 'Eat & Food'
  },
  {
    title: 'Quick Liks',
    care: 'How It Works ',
    business: 'Pricing Packages',
    education: 'Our Blog',
    food: 'Contact Us'
  },
  {
    title: 'Support',
    care: 'Terms and Conditions  ',
    business: 'Privacy Policy',
    education: 'Faq & Updates'
  }
])
</script>

<template>
  <footer class="listee">
    <div class="listee__container">
      <div class="listee__row">
        <div class="listee__body">
          <div class="listee__logo">
            <BaseIcon name="logoFooter" />
          </div>
          <div class="listee__phone">Phone: 09 555 5420</div>
          <div class="listee__email">Email: info@listee.com</div>
          <div class="listee__address">
            Address: Intersection 10 Hudson Yards, <br />
            26th Floor, New York, NY 10001
          </div>
        </div>
        <ul class="listee__list">
          <li v-for="item in categories" :key="item.title" class="listee__item">
            <a href="" class="listee__link">{{ item.title }}</a>
            <ul class="listee__sub-list">
              <li class="listee__sub-item">
                <a href="" class="listee__sub-link">{{ item.care }} </a>
              </li>
              <li class="listee__sub-item">
                <a href="" class="listee__sub-link">{{ item.business }}</a>
              </li>
              <li class="listee__sub-item">
                <a href="" class="listee__sub-link">{{ item.education }}</a>
              </li>
              <li class="listee__sub-item">
                <a href="" class="listee__sub-link">{{ item.food }}</a>
              </li>
            </ul>
          </li>
        </ul>
      </div>
      <div class="listee__border"></div>
      <div class="listee__bottom">
        <div class="listee__copyrght">© Listee 2022. All rights reserved</div>
        <div class="listee__icons">
          <BaseIcon v-for="item in icons" :key="item.name" :name="item.name" />
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.listee {
  background: #000924;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__row {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    padding: 50px;
    @media (max-width: 768px) {
      flex-wrap: wrap;
      padding: 20px;
      justify-content: center;
    }
  }
  &__border {
    border: 1px solid #ffffff;
    opacity: 0.15;
  }
  &__body {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 30px;
    color: rgba(255, 255, 255, 0.7);
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  &__logo {
    padding-bottom: 10px;
  }
  &__phone {
  }
  &__email {
  }
  &__address {
  }
  &__list {
    display: flex;
    justify-content: space-between;
    gap: 80px;
    @media (max-width: 768px) {
      flex-wrap: wrap;
      gap: 30px;
    }
  }
  &__item {
  }
  &__link {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 30px;
    color: #ffffff;
    padding-bottom: 10px;
  }
  &__sub-list {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  &__sub-item {
  }
  &__sub-link {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 40px;
    color: rgba(255, 255, 255, 0.7);
  }
}

.listee {
  &__bottom {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    padding: 50px;
    flex-wrap: wrap;
  }
  &__copyrght {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 30px;
    color: rgba(255, 255, 255, 0.7);
  }
  &__icons {
    display: flex;
    align-items: center;
    gap: 20px;
  }
}
</style>
