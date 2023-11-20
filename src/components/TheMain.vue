<script setup>
import BaseIcon from './BaseIcon.vue'
import { reactive } from 'vue'
const counts = reactive([
  {
    count: '8k+',
    placeName: 'Total Listings '
  },
  {
    count: '5.7k',
    placeName: 'PLace in the world'
  },
  {
    count: '9.9k',
    placeName: 'Happy Peoples'
  }
])
</script>

<template>
  <section class="listings">
    <div class="listings__contianer">
      <div class="listings__row">
        <div class="listings__content">
          <div class="listings__title">
            Explore Our <br />
            Verified Listings
          </div>
          <div class="listings__desc">
            There are plenty of location-specific and industry-specific business listing sites where you can submit your
            data.
          </div>
          <div class="listings__users users">
            <div class="users__title">
              Ratings
              <BaseIcon name="star" />
              5.0
            </div>
            <div class="users__desc">Trusted by Clients From Worldwide</div>
            <div class="users__images">
              <img src="../assets/img/user1.png" alt="" />
              <img src="../assets/img/user2.png" alt="" />
              <img src="../assets/img/user3.png" alt="" />
              <img src="../assets/img/user.png" alt="" />
              <div class="users__user-sum">+4k</div>
            </div>
          </div>
          <div class="listings__number numbers">
            <div class="numbers__number">+65-3002 56 56 376</div>
            <div class="numbers__desc">If you're in a hurry, quick call for us. We are here 24/7 to help you asap.</div>
          </div>
        </div>
        <div class="listings__image">
          <img src="../assets/img/building.png" alt="" />
        </div>
        <div class="listings__counts counts">
          <div class="counts__column">
            <div v-for="item in counts" :key="item.count" class="counts__body">
              <div class="counts__count">
                <p>{{ item.count }}</p>
                <span> {{ item.placeName }} </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.listings {
  padding: 100px 0;
  background: #fff5f7;
  &__contianer {
    max-width: 1400px;
    margin: 0 auto;
    overflow: hidden;
    padding: 2px 10px;
  }
  &__row {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    @media (max-width: 1280px) {
      flex-wrap: wrap;
      justify-content: center;
      padding-bottom: 50px;
    }
    @media (max-width: 1136px) {
    }
  }
  &__content {
    padding-top: 80px;
    max-width: 517px;
    @media (max-width: 1280px) {
      order: 2;
      max-width: 100%;
      padding-top: 0px;
    }
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 60px;
    line-height: 75px;
    color: #09153d;
    padding-bottom: 20px;
    @media (max-width: 1280px) {
      text-align: center;
    }
    @media (max-width: 768px) {
      font-size: 50px;
      br {
        display: none;
      }
    }
    @media (max-width: 425px) {
      font-size: 37px;
      line-height: 50px;
    }
  }
  &__desc {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 30px;
    color: #676c7b;
    padding-bottom: 30px;
  }
  &__users {
  }
  &__number {
  }
  &__image {
    width: 100%;
    img {
      width: 100%;
      object-fit: cover;
      object-position: center;
    }
    @media (max-width: 1280px) {
      order: 1;
    }
  }
  &__counts {
    @media (max-width: 1280px) {
      order: 3;
    }
  }
}
.users {
  padding-bottom: 30px;
  &__title {
    display: flex;
    align-items: center;
    gap: 5px;
    padding-bottom: 7px;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 22px;
    letter-spacing: 0.02em;
    color: #09153d;
    @media (max-width: 1280px) {
      justify-content: center;
    }
  }
  &__desc {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    letter-spacing: 0.02em;
    color: #676c7b;
    padding-bottom: 10px;
    @media (max-width: 1280px) {
      text-align: center;
    }
  }
  &__images {
    display: flex;
    align-items: center;
    @media (max-width: 1280px) {
      justify-content: center;
    }
    img {
      margin-right: -10px;
    }
  }
  &__user-sum {
    padding: 16px 11px;
    font-family: 'Space Grotesk';
    font-style: normal;
    font-weight: 700;
    font-size: 16px;
    line-height: 16px;
    letter-spacing: 0.02em;
    color: #ffffff;
    background-color: #ee1c47;
    border-radius: 50px;
  }
}
.numbers {
  @media (max-width: 1280px) {
    text-align: center;
  }
  &__number {
    font-family: 'Space Grotesk';
    font-style: normal;
    font-weight: 700;
    font-size: 16px;
    line-height: 20px;
    text-decoration-line: underline;
    color: #ee1c47;
    padding-bottom: 10px;
  }
  &__desc {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
    color: #676c7b;
  }
}
.counts {
  padding-top: 140px;
  @media (max-width: 1280px) {
    padding: 10px 0;
  }

  &__column {
    display: flex;
    flex-direction: column;
    gap: 80px;
    @media (max-width: 1280px) {
      flex-direction: row;
      flex-wrap: wrap;
      gap: 30px;
    }
    @media (max-width: 425px) {
      gap: 15px;
    }
  }
  &__body {
  }
  &__count {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 48px;
    line-height: 40px;
    text-align: center;
    p {
      color: #09153d;
      @media (max-width: 433px) {
        font-size: 25px;
        line-height: 10px;
      }
    }
    span {
      font-weight: 400;
      font-size: 16px;
      line-height: 30px;
      color: #676c7b;
      @media (max-width: 433px) {
        font-size: 12px;
      }
    }
  }
}
</style>
