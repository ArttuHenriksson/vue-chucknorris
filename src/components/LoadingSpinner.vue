<template>
  <div v-if="isLoading" class="flex justify-center items-center -mt-24">
    <img
      :src="iconPath"
      alt="Chuck Norris Loading Spinner"
      class="w-45 h-64 animate-pulse"
    />
  </div>
</template>

<script>
export default {
  props: {
    isLoading: {
      type: Boolean,
      default: true,
    },
    iconPath: {
      type: String,
      default: '/images/chucknorris.png', 
    },
  },
};
</script>

<style scoped>
</style>
