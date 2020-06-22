<template>
  <div id="app" class="bg-blue-100">
    <ratings-card class="max-w-xl" />
  </div>
</template>

<script>
import RatingsCard from '@/components/RatingsCard.vue'

export default {
  name: 'App',
  components: {
    RatingsCard
  }
}
</script>

<style>
#app {
  align-items: center;
  display: flex;
  justify-content: center;
  height: 100vh;
  width: 100vw;
}
</style>
