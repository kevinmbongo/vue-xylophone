<template>
  <div id="app">
    <article class="flex flex-col md:flex-row w-screen h-screen">
      <piano-key
        v-for="item in items"
        :key="item.noteUrl"
        :note-url="item.noteUrl"
        :color="item.color"
      />
    </article>
  </div>
</template>

<script>
import PianoKey from '@/components/core/PianoKey'

export default {
  name: 'App',

  components: { PianoKey },

  computed: {
    items() {
      return [
        {
          noteUrl: require('@/assets/sounds/note7.wav'),
          color: '#dc3030',
          accentColor: '',
          keyBordKey: 'S',
        },
        {
          noteUrl: require('@/assets/sounds/note6.wav'),
          color: '#6fdc30',
          accentColor: '',
        },
        {
          noteUrl: require('@/assets/sounds/note5.wav'),
          color: '#30a8dc',
          accentColor: '',
        },
        {
          noteUrl: require('@/assets/sounds/note4.wav'),
          color: '#dc3078',
          accentColor: '',
        },
        {
          noteUrl: require('@/assets/sounds/note3.wav'),
          color: '#dcb430',
          accentColor: '',
        },
        {
          noteUrl: require('@/assets/sounds/note2.wav'),
          color: '#dc6c30',
          accentColor: '',
        },
        {
          noteUrl: require('@/assets/sounds/note1.wav'),
          color: '#6130dc',
          accentColor: '',
        },
      ]
    },
  },
}
</script>
