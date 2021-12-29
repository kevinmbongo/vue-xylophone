<template>
  <button class="fixed top-10 left-10 bg-white z-10" @click="$emit('click')">
    menu
  </button>
</template>

<script>
export default {
  name: 'VButtonDrawer',
}
</script>

<style scoped></style>
