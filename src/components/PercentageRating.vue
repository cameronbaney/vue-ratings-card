<template>
  <div class="mb-5 flex items-center">
    <span class="text-blue-700">{{ stars }} star</span>
    <div class="bg-gray-200 flex-1 h-5 rounded-lg mx-3">
      <div class="bg-yellow-400 h-5 rounded-lg shadow-lg" :style="barStyle"></div>
    </div>
    <span>{{ percentage }}%</span>
  </div>
</template>

<script>
  export default {
    name: 'PercentageRating',

    props: {
      stars: {
        type: String,
        default: ''
      },
      percentage: {
        type: Number,
        default: 0
      }
    },

    computed: {
      barStyle: function() {
        return {
          width: `${this.percentage}%`
        }
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
