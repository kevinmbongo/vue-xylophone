<template>
  <div id="app">
    <article class="flex flex-col md:flex-row w-screen h-screen">
      <section class="bg-red-600 hover:bg-red-700" />
      <section class="bg-yellow-600 hover:bg-yellow-700" />
      <section class="bg-yellow-400 hover:bg-yellow-500" />
      <section class="bg-green-600 hover:bg-green-700" />
      <section class="bg-blue-600 hover:bg-blue-700" />
      <section class="bg-purple-600 hover:bg-purple-700" />
      <section class="bg-pink-600 hover:bg-pink-700" @click="playSound" />
    </article>
  </div>
</template>

<script>
export default {
  name: 'App',

  methods: {
    playSound() {
      console.log('coucou')
    },
  },
}
</script>

<style scoped>
section {
  @apply transition-all duration-300 ease-in-out flex-1 cursor-pointer;
}
</style>
