<template>
  <div class="ratings-card bg-white rounded-lg shadow-lg py-6 px-20">
    <h2 class="text-4xl text-center font-bold mb-5">Customer reviews</h2>

    <div class="rounded-full flex items-center justify-center bg-gray-200 p-4 mx-5 mb-1">
      <div class="star-wrap flex">
        <div class="star mx-1 h-8 w-8 bg-yellow-400"></div>
        <div class="star mx-1 h-8 w-8 bg-yellow-400"></div>
        <div class="star mx-1 h-8 w-8 bg-yellow-400"></div>
        <div class="star mx-1 h-8 w-8 bg-yellow-400"></div>
        <div class="star mx-1 h-8 w-8 bg-yellow-400"></div>
      </div>
      <span class="ml-5 text-gray-800">4.7 out of 5</span>
    </div>
    <p class="text-center">40 customer ratings</p>

    <div class="mt-16">
      <percentage-rating :stars="5" percentage="50" />
    </div>
  </div>
</template>

<script>
import PercentageRating from './PercentageRating'

export default {
  name: 'RatingsCard',

  components: {
    PercentageRating
  }
}
</script>

<style lang="scss" scoped>

</style>
