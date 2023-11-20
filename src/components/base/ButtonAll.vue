<script setup>
import BaseIcon from '../BaseIcon.vue'
import { defineProps } from 'vue'
const props = defineProps({
  title: {
    type: String,
    default: () => ''
  },
  icon: {
    type: String,
    default: () => ''
  },
  subscribe: {
    type: Boolean,
    default: () => false
  }
})
</script>

<template>
  <div :class="['header__btn', { primary: props.subscribe }]">
    <button>
      <BaseIcon v-if="props.icon" :name="props.icon" />
      {{ props.title }}
    </button>
  </div>
</template>

<style lang="scss" scoped>
.header {
  &__btn {
    @media (max-width: 479px) {
      flex: 0 1 100%;
    }
    button {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 18px;
      font-family: 'Inter';
      font-style: normal;
      font-weight: 700;
      font-size: 16px;
      line-height: 19px;
      color: #ffffff;
      background: #ee1c47;
      border-radius: 16px;
      @media (max-width: 768px) {
        padding: 13px;
        font-size: 14px;
      }
      @media (max-width: 479px) {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      @media (max-width: 425px) {
        padding: 10px 12px;
        font-size: 12px;
        span {
          display: none;
        }
      }
    }
  }
}
.primary {
  button {
    background-color: #ff823a;
  }
}
</style>
