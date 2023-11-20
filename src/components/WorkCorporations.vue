<script setup>
import ButtonAll from './base/ButtonAll.vue'
import BaseIcon from './BaseIcon.vue'
import { reactive } from 'vue'
const corporations = reactive([
  {
    image: 'baseyin.png',
    placeName: 'Hotel',
    icon: 'star',
    count: '4.8',
    title: 'Water Vibe Resorts',
    day: '$175/day',
    placeIcon: 'map',
    locationName: 'Washington Ave. Manchester, Kentucky',
    phoneIcon: 'phone',
    phoneName: '91 255 267 8790',
    userAvatar: 'user2.png',
    userName: 'Brooklyn Simmons',
    userDays: '5 days ago',
    arrow: 'arrowRight'
  },
  {
    image: 'baseyin.png',
    placeName: 'Food',
    icon: 'star',
    count: '4.8',
    title: 'Salmon and quinoa dish',
    day: '$175/day',
    placeIcon: 'map',
    locationName: 'Washington Ave. Manchester, Kentucky',
    phoneIcon: 'phone',
    phoneName: '91 255 267 8790',
    userAvatar: 'user3.png',
    userName: 'Elizabeth Gill',
    userDays: '5 days ago',
    arrow: 'arrowRight'
  },
  {
    image: 'baseyin.png',
    placeName: 'Wedding',
    icon: 'star',
    count: '4.8',
    title: 'Creative Wedding Planner',
    day: '$175/day',
    placeIcon: 'map',
    locationName: 'Washington Ave. Manchester, Kentucky',
    phoneIcon: 'phone',
    phoneName: '91 255 267 8790',
    userAvatar: 'user.png',
    userName: 'Esther Howard',
    userDays: '5 days ago',
    arrow: 'arrowRight'
  },
  {
    image: 'baseyin.png',
    placeName: 'Business',
    icon: 'star',
    count: '4.8',
    title: 'AJ Corporation',
    day: '$175/day',
    placeIcon: 'map',
    locationName: 'Washington Ave. Manchester, Kentucky',
    phoneIcon: 'phone',
    phoneName: '91 255 267 8790',
    userAvatar: 'user1.png',
    userName: 'Leslie Alexander',
    userDays: '5 days ago',
    arrow: 'arrowRight'
  },
  {
    image: 'baseyin.png',
    placeName: 'Hospital',
    icon: 'star',
    count: '4.8',
    title: 'Medison Diagnostics',
    day: '$175/day',
    placeIcon: 'map',
    locationName: 'Washington Ave. Manchester, Kentucky',
    phoneIcon: 'phone',
    phoneName: '91 255 267 8790',
    userAvatar: 'wade_warren.png',
    userName: 'Wade Warren',
    userDays: '5 days ago',
    arrow: 'arrowRight'
  },
  {
    image: 'baseyin.png',
    placeName: 'Office',
    icon: 'star',
    count: '4.8',
    title: 'Smart Work Office',
    day: '$175/day',
    placeIcon: 'map',
    locationName: 'Washington Ave. Manchester, Kentucky',
    phoneIcon: 'phone',
    phoneName: '91 255 267 8790',
    userAvatar: 'jane.png',
    userName: 'Jane Cooper',
    userDays: '5 days ago',
    arrow: 'arrowRight'
  }
])
</script>

<template>
  <section class="corporations">
    <div class="corporations__container">
      <header class="corporations__header header-corporations">
        <div class="header-corporations__row">
          <div class="header-corporations__content">
            <div class="header-corporations__title">
              Available Listings
              <BaseIcon name="line" />
            </div>
            <div class="header-corporations__desc">
              Morbi mollis vestibulum sollicitudin. Nunc in eros a justo facilisis rutrum. Aenean id ullamcorper libero
              Vestibulum imperdiet nibh vel magna lacinia commodo ultricies,
            </div>
          </div>
          <div class="header-corporations__btn">
            <ButtonAll title="Explore All Listings" />
          </div>
        </div>
      </header>
      <div class="corporations__work-places work-places">
        <div class="work-places__column">
          <div v-for="item in corporations" :key="item.userName" class="work-places__body">
            <div class="work-places__image">
              <img :src="require(`../assets/img/${item.image}`)" alt="" />
              <div class="work-places__name-count">
                <div class="work-places__name">{{ item.placeName }}</div>
                <div class="work-places__count">
                  <BaseIcon :name="item.icon" />
                  <p>{{ item.count }}</p>
                </div>
              </div>
            </div>
            <div class="work-places__content">
              <div class="work-places__box">
                <div class="work-places__title-day">
                  <div class="work-places__title">{{ item.title }}</div>
                  <div class="work-places__day">{{ item.day }}</div>
                </div>
                <div class="work-places__location">
                  <BaseIcon :name="item.placeIcon" />
                  <p>{{ item.locationName }}</p>
                </div>
                <div class="work-places__call">
                  <BaseIcon :name="item.phoneIcon" />
                  <p>{{ item.phoneName }}</p>
                </div>
              </div>
              <div class="work-places__profile profile">
                <div class="profile__user">
                  <div class="profile__icon">
                    <img :src="require(`../assets/img/${item.userAvatar}`)" alt="" />
                  </div>
                  <div class="profile__name">
                    <p>{{ item.userName }}</p>
                    <span>{{ item.userDays }}</span>
                  </div>
                </div>
                <div class="profile__arrow">
                  <BaseIcon name="arrowRight" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.corporations {
  padding-top: 100px;
  padding-bottom: 100px;
  &__container {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__header {
  }
  &__work-places {
  }
}
.header-corporations {
  padding-bottom: 45px;
  &__row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    @media (max-width: 960px) {
      flex-direction: column;
      justify-content: center;
    }
  }
  &__content {
    max-width: 755px;
    display: flex;
    flex-direction: column;
    gap: 30px;
    @media (max-width: 960px) {
      justify-content: center;
      max-width: 100%;
      gap: 10px;
    }
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 48px;
    line-height: 60px;
    color: #09153d;
    span {
      margin-top: -15px;
      float: left;
      @media (max-width: 960px) {
        justify-content: center;
        float: none;
      }
    }
    @media (max-width: 960px) {
      text-align: center;
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
  &__btn {
    padding-top: 20px;
  }
}
.work-places {
  width: 100%;
  &__column {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 30px;
    flex-wrap: wrap;
  }
  &__body {
  }
  &__image {
    position: relative;
    height: 350px;
    width: 100%;
    @media (max-width: 768px) {
      height: 100%;
    }
    img {
      width: 100%;
      height: 100%;
    }
  }
  &__name-count {
    position: absolute;
    bottom: 90px;
    left: 20px;
    width: 90%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    @media (max-width: 768.99px) {
      bottom: 100px;
    }
    @media (max-width: 350px) {
      bottom: 70px;
    }
  }
  &__name {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 28px;
    color: #ffffff;
    background: #ff823a;
    backdrop-filter: blur(15px);
    border-radius: 40px;
    padding: 6px 16px;
  }
  &__count {
    display: flex;
    align-items: center;
    gap: 5px;
    padding: 7px 12px;
    background: #ffffff;
    border-radius: 30px;
    p {
      font-family: 'Inter';
      font-style: normal;
      font-weight: 500;
      font-size: 16px;
      line-height: 16px;
      color: #676c7b;
    }
  }
  &__content {
  }
  &__box {
    margin-top: -80px;
    padding: 24px;
    background: #ffffff;
    box-shadow: 0px 30px 70px rgba(2, 13, 46, 0.04);
  }
  &__title-day {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-bottom: 8px;
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 30px;
    color: #09153d;
    @media (max-width: 350px) {
      font-size: 17px;
    }
  }
  &__day {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 30px;
    color: #ee1c47;
    @media (max-width: 350px) {
      font-size: 17px;
    }
  }
  &__location {
    display: flex;
    align-items: center;
    gap: 5px;
    p {
      font-family: 'Inter';
      font-style: normal;
      font-weight: 400;
      font-size: 16px;
      line-height: 28px;
      color: #676c7b;
      @media (max-width: 350px) {
        font-size: 12px;
      }
    }
  }
  &__call {
    padding-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 5px;
    padding-left: 5px;
    p {
      font-family: 'Inter';
      font-style: normal;
      font-weight: 400;
      font-size: 16px;
      line-height: 28px;
      color: #676c7b;
      @media (max-width: 350px) {
        font-size: 12px;
      }
    }
  }
  &__profile {
  }
}
.profile {
  background: rgba(103, 108, 123, 0.05);
  box-shadow: 0px 30px 70px rgba(2, 13, 46, 0.04);
  border-radius: 0px 0px 24px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 24px;
  width: 100%;
  @media (max-width: 350px) {
    padding: 12px 7px;
  }
  &__user {
    display: flex;
    align-items: center;
    gap: 5px;
  }
  &__icon {
  }
  &__name {
    p {
      font-family: 'Inter';
      font-style: normal;
      font-weight: 500;
      font-size: 16px;
      line-height: 16px;
      color: #09153d;
      padding-bottom: 5px;
    }
    span {
      font-family: 'Inter';
      font-style: normal;
      font-weight: 400;
      font-size: 12px;
      line-height: 16px;
      color: #676c7b;
    }
  }
  &__arrow {
    &:nth-child(even) {
      color: #676c7b;
    }
  }
}
</style>
