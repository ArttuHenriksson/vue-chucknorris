<template>
  <div class="flex flex-col items-center text-center space-y-4">
    <div v-if="loading">
      <LoadingSpinner :isLoading="loading" />
    </div>

    <div v-else class="text-m font-mono flex justify-center">
      {{ joke }}
    </div>

    <RandomJokeButton @click="fetchJoke" />
  </div>
</template>

<script>
import RandomJokeButton from './RandomJokeButton.vue';
import LoadingSpinner from './LoadingSpinner.vue';

export default {
  components: {
    RandomJokeButton,
    LoadingSpinner,
  },
  data() {
    return {
      joke: '',
      loading: false,
    };
  },
  mounted() {
    this.fetchJoke();
  },
  methods: {
    fetchJoke() {
      this.loading = true;
      fetch('https://api.chucknorris.io/jokes/random?category=dev')
        .then((response) => response.json())
        .then((data) => {
          setTimeout(() => {
            this.joke = data.value;
            this.loading = false;
          }, 2500);
        })
        .catch((error) => {
          console.error(error);
          this.loading = false;
        });
    },
  },
};
</script>
