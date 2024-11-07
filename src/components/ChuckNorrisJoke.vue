<template>
  <div>
    {{ joke }}
    <RandomJokeButton @click="fetchJoke" />
  </div>
</template>

<script lang="js">
import RandomJokeButton from './RandomJokeButton.vue';
export default {
          components: {RandomJokeButton,},
          data() {
    return {
      joke: ''
    }
  },

  mounted() {
    this.fetchJoke()
  },
  methods: {
    fetchJoke() {
      fetch('https://api.chucknorris.io/jokes/random')
        .then(response => response.json())
        .then(data => {
          this.joke = data.value
        })
        .catch(error => console.error(error))
    }
  }
}
</script>
