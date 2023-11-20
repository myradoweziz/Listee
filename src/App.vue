<script setup>
import TheHeader from './components/TheHeader.vue'
import TheMain from './components/TheMain.vue'
import TheColumns from './components/TheColumns.vue'
import TheCategories from './components/TheCategories.vue'
import BestForm from './components/BestForm.vue'
import WorkCorporations from './components/WorkCorporations.vue'
import NewsLetter from './components/NewsLetter.vue'
import WorkListings from './components/WorkListings.vue'
import UsersFeedbacks from './components/UsersFeedbacks.vue'
import LatestBlogs from './components/LatestBlogs.vue'
import TheFooter from './components/TheFooter.vue'
</script>
<template>
  <div class="wrapper">
    <TheHeader />
    <TheMain />
    <TheColumns />
    <TheCategories />
    <BestForm />
    <WorkCorporations />
    <NewsLetter />
    <WorkListings />
    <UsersFeedbacks />
    <LatestBlogs />
    <TheFooter />
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  overflow: hidden;
}
</style>
