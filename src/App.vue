<script setup lang="ts">
import AppFooter from './components/layout/AppFooter.vue';
import AppMain from './components/layout/AppMain.vue';

</script>

<template>
  <div class="app">
    <AppMain>
      <section class="w-full bg-purple-100">
        <div class="w-full min-h-57.5 pt-6 px-6 pb-0 bg-[url('@/assets/images/background-pattern-desktop.svg')] bg-no-repeat bg-position-[center_-60px] md:min-h-80 md:bg-position-[center_top]"></div>
        <div class="relative px-6 pt-0 pb-6">

        </div>
      </section>
    </AppMain>
    <AppFooter/>
  </div>
</template>

<style lang="scss" scoped>
  .app {
    display: flex;
    flex-direction: column;
    min-width: 360px;
    max-width: 1440px;
    min-height: 100vh;
    margin: 0 auto;
  }
</style>