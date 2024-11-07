<template>
  <div class="flex justify-center text-center">
    <button
      @click="$emit('click')"
      class="bg-orange-500 text-white font-bold py-2 px-4 rounded mt-6"
    >
      Get a new joke!
    </button>
  </div>
</template>

<script>
export default {
  name: 'JokeButton',
};
</script>
