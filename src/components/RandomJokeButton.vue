<template>
  <div class="flex justify-center text-center">
    <button
      @click="$emit('click')"
      class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded mt-6"
    >
      Get a new joke!
    </button>
  </div>

  <!-- <img
    class="mt-6 rounded-xl"
    src="https://media.tenor.com/93Dd5zxeydEAAAAM/chuck-thumb-thumbs-up.gif"
    alt="Chuck Norris Thumbs Up"
  /> -->
</template>

<script>
export default {
  name: 'JokeButton',
};
</script>
