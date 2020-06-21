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
      <span class="ml-5 text-gray-800">{{ totalStarRating }} out of 5</span>
    </div>
    <p class="text-center">{{ totalRatings }} customer rating<template v-if="totalRatings !== 1">s</template></p>

    <div class="mt-16">
      <percentage-rating v-for="rating in Object.keys(ratings)" :key="rating" :stars="rating" :percentage="getPercentage(ratings[rating])" />
    </div>
  </div>
</template>

<script>
import PercentageRating from './PercentageRating'

export default {
  name: 'RatingsCard',

  components: {
    PercentageRating
  },

  data() {
    return {
      ratings: {
        5: 100,
        4: 50,
        3: 25,
        2: 10,
        1: 1
      }
    }
  },

  computed: {
    /**
     * Compute total number of ratings
     * @returns {Number}
     */
    totalRatings: function() {
      const allRatings = Object.values(this.ratings)
      return allRatings.reduce((total, current) => {
        return total + current
      })
    },

    /**
     * Compute total star rating out of 5
     * @returns {Number}
     */
    totalStarRating: function() {
      const total = Object.keys(this.ratings).reduce((previous, key) => {
        return this.ratings[key] * key + previous
      }, 0)

      return Math.round(total / this.totalRatings, 1)
    }
  },

  methods: {
    /**
     * Get percentage of rating
     * @param {Number} rating
     * @returns {Number}
     */
    getPercentage: function(rating) {
      return Math.floor(rating / this.totalRatings * 100)
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
