<template>
  <div id="app">
    <article class="flex flex-col md:flex-row w-screen h-screen">
      <v-piano-key
        v-for="item in instrumentDataBase[currentInstrumentIndex].keys"
        :key="item.noteUrl"
        :note-url="item.noteUrl"
        :color="item.color"
        :key-bord-key="item.keyBordKey"
        :current-key="currentKey"
        @reset-current-index="currentKey = ''"
      />

      <v-button-drawer @click="drawerIsOpen = !drawerIsOpen" />

      <v-drawer v-if="drawerIsOpen === true" v-model="currentInstrumentIndex" />
    </article>
  </div>
</template>

<script>
import VPianoKey from '@/components/core/VPianoKey'
import VButtonDrawer from '@/components/core/VButtonDrawer'
import VDrawer from '@/components/core/VDrawer'

export default {
  name: 'App',

  components: { VDrawer, VButtonDrawer, VPianoKey },

  data: () => ({
    drawerIsOpen: false,

    currentInstrumentIndex: 0,

    currentKey: '',

    instrumentDataBase: [
      {
        id: 'xylophone',
        keys: [
          {
            noteUrl: require('@/assets/sounds/xylophone/note7.wav'),
            color: '#dc3030',
            accentColor: '',
            keyBordKey: 'z',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note6.wav'),
            color: '#6fdc30',
            accentColor: '',
            keyBordKey: 'e',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note5.wav'),
            color: '#30a8dc',
            accentColor: '',
            keyBordKey: 'r',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note4.wav'),
            color: '#dc3078',
            accentColor: '',
            keyBordKey: 'y',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note3.wav'),
            color: '#dcb430',
            accentColor: '',
            keyBordKey: 'u',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note2.wav'),
            color: '#dc6c30',
            accentColor: '',
            keyBordKey: 'i',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note1.wav'),
            color: '#6130dc',
            accentColor: '',
            keyBordKey: 'o',
          },
        ],
      },
      {
        id: 'soundbox',
        keys: [
          {
            noteUrl: require('@/assets/sounds/soundbox/AmongUs.wav'),
            color: '#dc3030',
            accentColor: '',
            keyBordKey: 'z',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/BoneCrack.wav'),
            color: '#6fdc30',
            accentColor: '',
            keyBordKey: 'e',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/CartoonSlip.wav'),
            color: '#30a8dc',
            accentColor: '',
            keyBordKey: 'r',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/DuckToySqueak.wav'),
            color: '#dc3078',
            accentColor: '',
            keyBordKey: 'y',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/HelloThere.wav'),
            color: '#dcb430',
            accentColor: '',
            keyBordKey: 'u',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/QuickReverbFart.wav'),
            color: '#dc6c30',
            accentColor: '',
            keyBordKey: 'i',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/WetFartMeme.wav'),
            color: '#6130dc',
            accentColor: '',
            keyBordKey: 'o',
          },
        ],
      },
    ],
  }),

  mounted() {
    const body = document.getElementsByTagName('body')[0]
    body.addEventListener('keypress', this.handleKeyPress)
  },

  methods: {
    handleKeyPress(event) {
      this.currentKey = event.key
    },
  },
}
</script>
