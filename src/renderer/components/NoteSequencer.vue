<template>
  <window v-model="size">
    <template slot="toolbar">
      <v-icon>select</v-icon>
      <v-icon>slice</v-icon>
    </template>
    <div style="display: flex">
      <div>
        <piano v-for="octave in octaves" :key="octave" :octave="octave"></piano>
      </div>
      <div>
        <sequencer v-for="octave in octaves" :key="octave" :size="25"></sequencer>
      </div>
    </div>
  </window>
</template>

<script>
  import Window from '@/components/Window'
  import Piano from '@/components/Piano'
  import Sequencer from '@/components/Sequencer'

  export default {
    name: 'NoteSequencer',
    components: {Window, Piano, Sequencer},
    data () {
      return {
        octaves: [4, 5].reverse(),
        divsPerMeasure: 4,
        numMeasures: 4,
        size: {height: 500, width: 500}
      }
    }
  }
</script>
