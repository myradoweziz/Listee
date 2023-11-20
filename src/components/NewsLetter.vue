<script setup>
  import ButtonAll from './base/ButtonAll.vue'
  import BaseIcon from './BaseIcon.vue'
</script>

<template>
  <section class="news-letter">
    <div class="news-letter__container">
      <div class="news-letter__row">
        <div class="news-letter__left">
          <div class="news-letter__content">
            <div class="news-letter__title">
              Get Our Monthly Newsletter
              <BaseIcon name="line" />
            </div>
            <br />
            <div class="news-letter__desc">
              Select a category that best suits your interest. Use filters to customize your search and to find exactly
              what you want.
            </div>
            <div class="news-letter__submit-btn">
              <div class="news-letter__submit">
                <input type="text" placeholder="Enter email address" />
              </div>
              <ButtonAll title="Subscribe" subscribe="" />
            </div>
          </div>
        </div>
        <div class="news-letter__right">
          <div class="news-letter__video">
            <img src="../assets/img/video.png" alt="" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
  .news-letter {
    padding-bottom: 100px;
    &__row {
      background-color: #fff5f7;
      display: flex;
      justify-content: space-between;
      gap: 5px;
      @media (max-width: 1101px) {
        flex-wrap: wrap;
        flex-direction: column;
        justify-content: center;
      }
    }
    &__container {
      max-width: 1400px;
      margin: 0 auto;
      overflow: hidden;
    }
    &__left {
      flex: 0 0 50%;
      overflow: hidden;
      padding: 50px;
      width: 100%;
      @media (max-width: 1101px) {
        flex: 0 0 100%;
      }
    }

    &__content {
      max-width: 550px;
      @media (max-width: 1101px) {
        max-width: 100%;
      }
    }
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
        float: left;
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
    &__submit-btn {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      @media (max-width: 768px) {
        flex-wrap: wrap;
      }
    }
    &__submit {
      @media (max-width: 479px) {
        width: 100%;
      }
      input {
        padding: 15px 25px;
        background: #ffffff;
        border-radius: 16px;
        font-family: 'Inter';
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 30px;
        color: #676c7b;
        @media (max-width: 768px) {
          width: 100%;
        }
      }
    }

    &__right {
      flex: 0 0 50%;
    }
    &__video {
      width: 100%;
      height: 100%;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
      }
    }
  }
</style>
