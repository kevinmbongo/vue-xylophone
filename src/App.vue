<template>
  <div id="app">
    <article class="flex flex-col md:flex-row w-screen h-screen">
      <V-piano-key
        v-for="item in instrumentDataBase[currentInstrumentIndex].keys"
        :key="item.noteUrl"
        :note-url="item.noteUrl"
        :color="item.color"
      />
      <v-button-drawer @click="drawerIsOpen = !drawerIsOpen" />
      <v-drawer
        v-show="drawerIsOpen === true"
        :current-instrument-index="currentInstrumentIndex"
      />
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
    instrumentDataBase: [
      {
        id: 'xylophon',
        keys: [
          {
            noteUrl: require('@/assets/sounds/xylophone/note7.wav'),
            color: '#dc3030',
            accentColor: '',
            keyBordKey: 'S',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note6.wav'),
            color: '#6fdc30',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note5.wav'),
            color: '#30a8dc',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note4.wav'),
            color: '#dc3078',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note3.wav'),
            color: '#dcb430',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note2.wav'),
            color: '#dc6c30',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/xylophone/note1.wav'),
            color: '#6130dc',
            accentColor: '',
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
            keyBordKey: 'S',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/BoneCrack.wav'),
            color: '#6fdc30',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/CartoonSlip.wav'),
            color: '#30a8dc',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/DuckToySqueak.wav'),
            color: '#dc3078',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/HelloThere.wav'),
            color: '#dcb430',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/QuickReverbFart.wav'),
            color: '#dc6c30',
            accentColor: '',
          },
          {
            noteUrl: require('@/assets/sounds/soundbox/WetFartMeme.wav'),
            color: '#6130dc',
            accentColor: '',
          },
        ],
      },
    ],
  }),
}
</script>
