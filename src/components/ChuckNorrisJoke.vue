<template>
  <div class="flex flex-col items-center text-center space-y-4">
    <div :class="loading ? 'block' : 'hidden'">
      <LoadingSpinner :isLoading="loading" />
    </div>
    <div
      :class="[
        'text-m font-mono flex justify-center transition-opacity duration-300',
        loading ? 'opacity-0' : 'opacity-100',
      ]"
      style="min-height: 1.5rem"
    >
      {{ joke }}
    </div>
<div>
  <select v-model="category" @change="fetchJoke">
    <option value="animal">Animal</option>
    <option value="career">Career</option>
    <option value="celebrity">Celebrity</option>
    <option value="dev">Dev</option>
    <option value="explicit">Explicit</option>
    <option value="fashion">Fashion</option>
    <option value="food">Food</option>
    <option value="money">Money</option>
  </select>
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
      const c = this.category ? `?category=${this.category}` : '';
      fetch(`https://api.chucknorris.io/jokes/random${c}`)
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
