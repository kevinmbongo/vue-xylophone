<template>
  <nav>
    <button>
      <img src="@/assets/images/guitar.png" alt="guitar" />
      <p>Guitar</p>
    </button>
    <button @click="currentInstrumentIndex = 1">
      <img src="@/assets/images/piano.png" alt="piano" />
      <p>Soundbox</p>
    </button>
    <button @click="currentInstrumentIndex = 0">
      <img src="@/assets/images/xylophone.png" alt="xylophone" />
      <p>Xylophone</p>
    </button>
  </nav>
</template>

<script>
export default {
  name: 'VDrawer',
  props: {
    currentInstrumentIndex: {
      type: Number,
      required: true,
    },
  },
}
</script>

<style scoped>
button {
  @apply flex items-center m-5;
}

p {
  @apply mx-5;
}
</style>
