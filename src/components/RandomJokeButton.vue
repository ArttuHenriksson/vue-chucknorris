<template>
  <button @click="$emit('click')">Get a new joke!</button>
</template>

<script>
export default {
  name: 'JokeButton',
};
</script>
