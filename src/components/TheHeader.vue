<script setup>
import { reactive, ref } from 'vue'
import ListeeLogo from '@/components/base/ListeeLogo.vue'
import BaseIcon from './BaseIcon.vue'
import ButtonAll from './base/ButtonAll.vue'
const menuItems = reactive([
  { id: 0, title: 'Home', activeClass: true, sort: true },
  { id: 1, title: 'Listings' },
  { id: 2, title: 'Pages', sort: true },
  { id: 3, title: 'Contact' }
])

const activeBurger = ref(false)
const scrollTrigger = ref(80)
window.onscroll = function () {
  window.scrollY >= scrollTrigger.value || window.pageYOffset >= scrollTrigger.value
    ? document.querySelector('.header').classList.add('scroll')
    : document.querySelector('.header').classList.remove('scroll')
}
</script>
<template>
  <div :class="['header', { active: activeBurger }]">
    <div class="header__container">
      <div class="header__row">
        <div class="header__log-menu">
          <div class="header__logo">
            <ListeeLogo />
          </div>
          <div class="header__body">
            <ul class="header__menu">
              <li v-for="item in menuItems" :key="item.title" class="header__item">
                <a href="" :class="['header__link ', { active_link: item.activeClass }]">
                  {{ item.title }}
                  <BaseIcon v-if="item.sort" name="arrowBottom" />
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div class="header__user-burger">
          <div class="header__user-btn">
            <div class="header__user user">
              <div class="user__row">
                <div class="user__image">
                  <img src="../assets/img/user.png" alt="" />
                </div>
                <div class="user__name">
                  Nader Azzeh
                  <BaseIcon name="arrowBottom" />
                </div>
              </div>
            </div>
            <ButtonAll title="Add Listing" icon="plus" />
          </div>
          <div class="header__burger" @click="activeBurger = !activeBurger">
            <BaseIcon :name="activeBurger ? 'close' : 'burger'" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.header {
  position: fixed;
  padding: 10px 5px;
  padding-bottom: 5px;
  top: 0;
  left: 0;
  z-index: 10;
  width: 100%;
  transition: 0.3s ease 0s;
  background: #fff5f7;
  &.active {
    .header__logo {
      @media (max-width: 850px) {
        display: none;
      }
    }
    .header {
    }

    .header__body {
      @media (max-width: 850px) {
        background-color: #fff5f7;
        left: 0;
        transition: left 0.3s;
      }
    }
    .header__menu {
      @media (max-width: 850px) {
        padding-top: 70px;
        display: flex;
        flex-direction: column;
        align-items: center;
        z-index: 3;
        gap: 50px;
      }
    }
    .header__link {
      font-size: 25px;
    }
    .header__btn {
      @media (max-width: 850px) {
        display: none;
      }
    }
  }
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__user-burger {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  &__log-menu {
    display: flex;
    align-items: center;
    gap: 80px;
    @media (max-width: 1150px) {
      gap: 30px;
    }
  }
  &__burger {
    display: none;
    color: #000;
    @media (max-width: 990px) {
      display: inline;
      position: relative;
      z-index: 10;
    }
    @media (max-width: 768px) {
      span {
        :deep(svg) {
          width: 40px;
          height: 30px;
        }
      }
    }
    @media (max-width: 425px) {
      span {
        :deep(svg) {
          width: 35px;
          height: 30px;
        }
      }
    }
  }
  &__logo {
    @media (max-width: 768px) {
      width: 130px;
    }
    @media (max-width: 425px) {
      width: 80px;
    }
  }
  &__row {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__body {
    @media (max-width: 990px) {
      position: fixed;
      width: 100%;
      left: -100%;
      transition: left 0.3s ease 0s;
      top: 0;
      background-color: #fff;
      height: 100%;
      z-index: 2;
    }
  }

  &__menu {
    display: flex;
    align-items: center;
    gap: 60px;
    list-style: none;
    padding: 0;
    @media (max-width: 1150px) {
      gap: 30px;
    }
    @media (max-width: 990px) {
      display: none;
    }
  }

  &__link {
    &.active_link {
      background: #ffe1e8;
      border-radius: 20px;
      color: #ee1c47;
      padding: 11px 22px;
    }
    &:hover {
      border-bottom: 1px solid #09153d;
    }
    display: flex;
    align-items: center;
    gap: 5px;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    color: #09153d;
    text-decoration: none;
  }

  &__user-btn {
    display: flex;
    align-items: center;
    gap: 30px;
    @media (max-width: 425px) {
      gap: 10px;
    }
  }
}
.user {
  &__row {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  &__image {
    position: relative;
    img {
      width: 100%;
      height: 100%;
    }
    @media (max-width: 768px) {
      width: 40px;
      height: 40px;
    }
    &::after {
      content: '';
      position: absolute;
      bottom: 0;
      right: 5px;
      width: 12px;
      height: 12px;
      background: #38b653;
      border-radius: 40px;
    }
  }
  &__name {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    color: #09153d;
    @media (max-width: 768px) {
      font-size: 13px;
      display: none;
    }
  }
}
.scroll {
  background: #fff;
}
</style>
