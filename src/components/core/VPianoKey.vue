<template>
  <section
    class="flex justify-between items-center px-7 md:flex-col md:py-16 hover:opacity-hs90"
    :style="{ background: color }"
    @click="playSound"
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

    keyBordKey: {
      type: String,
      required: true,
    },

    currentKey: {
      type: String,
      required: true,
    },
  },

  watch: {
    currentKey() {
      this.handleKeyPress()
    },
  },

  methods: {
    playSound() {
      let audio = new Audio(this.noteUrl)

      audio.play()
    },

    handleKeyPress() {
      if (this.keyBordKey === this.currentKey) {
        this.playSound()

        this.$emit('reset-current-index')
      }
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
