<template>
  <section
    class="flex justify-between items-center px-7 md:flex-col md:py-16 hover:opacity-hs90"
    :style="{ background: color }"
    @keydown="test"
  >
    <div class="nailStyle"></div>
    <div class="nailStyle"></div>
  </section>
</template>

<script>
export default {
  name: 'PianoKey',

  props: {
    noteUrl: {
      type: String,
      required: true,
    },

    color: {
      type: String,
      required: true,
    },
  },

  methods: {
    playSound() {
      let audio = new Audio(this.noteUrl)

      audio.play()
    },

    test(event) {
      console.log(event)
    },
  },
}
</script>

<style scoped>
section {
  @apply transition-all duration-300 ease-in-out flex-1 cursor-pointer;
}
.nailStyle {
  @apply bg-gray-300 w-7 h-7 rounded-full;
}
</style>
