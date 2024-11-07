<script setup>
import ChuckNorrisJuke from './components/ChuckNorrisJoke.vue';
import Header from './components/Header.vue';
import './style.css';
</script>

<template>
  <header class="flex justify-center text-center">
    <Header />
  </header>
  <main class="justify-center flex text-center mt-72">
    <div>
      <ChuckNorrisJuke />
    </div>
  </main>
</template>
<style scoped>
:global(body) {
  background-color: antiquewhite;
}
</style>
