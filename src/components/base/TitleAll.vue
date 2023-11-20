<script setup>
import BaseIcon from '../BaseIcon.vue'
import { defineProps } from 'vue'
const props = defineProps({
  title: {
    type: String,
    default: () => ''
  }
})
</script>

<template>
  <div class="header-category__title">
    {{ props.title }}
    <BaseIcon name="line" />
  </div>
</template>

<style lang="scss" scoped>
.header-category {
  &__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 800;
    font-size: 48px;
    line-height: 60px;
    color: #09153d;
    z-index: 20;
    span {
      :deep(svg) {
        z-index: -1;
      }
      margin-top: -15px;
      padding-bottom: 20px;
      justify-content: center;
    }
    @media (max-width: 768px) {
      font-size: 38px;
    }
  }
}
</style>
