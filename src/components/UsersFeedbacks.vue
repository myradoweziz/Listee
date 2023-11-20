<script setup>
import BaseIcon from './BaseIcon.vue'
import { reactive } from 'vue'
const users = reactive([
  {
    icon: 'quote',
    desc: 'I have traveled and explored several destinations using this platform, no doubt it is highly recommended for traveling because it is comfortable and the service is great.',
    avatar: 'user1.png',
    title: 'Adam L. Brian',
    mission: 'Traveller'
  },
  {
    icon: 'quote',
    desc: 'I have traveled and explored several destinations using this platform, no doubt it is highly recommended for traveling because it is comfortable and the service is great.',
    avatar: 'user2.png',
    title: 'Adam L. Brian',
    mission: 'Traveller'
  }
])
</script>

<template>
  <section class="feedback">
    <div class="feedback__row">
      <div class="feedback__content">
        <div class="feedback__container">
          <div class="feedback__title">
            Users Feedbacks
            <BaseIcon name="line" />
          </div>
          <div class="feedback__desc">
            Morbi mollis vestibulum sollicitudin. Nunc in eros a justo facilisis rutrum. Aenean id ullamcorper libero
            Vestibulum imperdiet nibh vel magna lacinia commodo ultricies,
          </div>
          <div class="feedback__arrows">
            <BaseIcon name="chevronLeft" />
            <BaseIcon name="chevronRightActive" />
          </div>
        </div>
      </div>
      <div class="feedback__users users">
        <div class="users__box">
          <div v-for="item in users" :key="item.avatar" class="users__body">
            <div class="users__icon">
              <BaseIcon :name="item.icon" />
            </div>
            <div class="users__desc">
              {{ item.desc }}
            </div>
            <div class="users__profile">
              <div class="users__avatar">
                <img :src="require(`../assets/img/${item.avatar}`)" alt="" />
              </div>
              <div class="users__title">
                {{ item.title }}
                <span>{{ item.mission }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.feedback {
  padding-bottom: 100px;
  &__row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
    background: rgba(255, 130, 58, 0.05);
    padding-bottom: 100px;
    @media (max-width: 1024px) {
      flex-wrap: wrap;
    }
  }
  &__content {
    padding: 20px;
    width: 100%;
  }
  &__container {
    overflow: hidden;
  }
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 48px;
    line-height: 60px;
    color: #09153d;
    display: flex;
    flex-direction: column;
    @media (max-width: 1024px) {
      align-items: center;
    }
    span {
      margin-top: -15px;
      float: left;
      @media (max-width: 1024px) {
        float: none;
      }
    }

    padding-bottom: 30px;
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
  &__arrows {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  &__users {
  }
}
.users {
  &__box {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
  }
  &__body {
    padding: 40px;
    background: #ffffff;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
  }
  &__icon {
    padding-bottom: 30px;
  }
  &__desc {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 30px;
    color: #676c7b;
    padding-bottom: 8px;
  }
  &__profile {
    display: flex;
    align-items: center;
    gap: 5px;
  }
  &__avatar {
  }
  &__content {
  }
  &__title {
    display: flex;
    flex-direction: column;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 16px;
    line-height: 30px;
    color: #09153d;
    span {
      font-weight: 400;
      font-size: 14px;
      line-height: 14px;
      color: #676c7b;
    }
  }
}
</style>
