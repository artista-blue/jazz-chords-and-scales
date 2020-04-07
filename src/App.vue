<template>
<div id="app">
  <header style='display:inline;'>
    <h1>The Jazz Chords and Scales</h1>
    <InstrumentSelector :selectHandler='this.selectInstrument' class='InstrumentSelector'/>
  </header>
  <main>
    <PianoView ref='pianoView'/>
    <GuitarView ref='guitarView'/>    
  </main>
  <footer>
  </footer>
</div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import InstrumentSelector from './components/InstrumentSelector.vue';
  import PianoView from './components/PianoView.vue';
  import GuitarView from './components/GuitarView.vue';

  export default Vue.extend({
    name: 'App',
    mounted () {
      this.$refs.pianoView.show();
    },
    data () {
      return {
        instrumentType: 'piano'
      };
    },
    components: {
      InstrumentSelector,
      PianoView,
      GuitarView
    },
    methods: {
      selectInstrument (instrumentType: string) {
        this.instrumentType = instrumentType;
        console.log(this.instrumentType);
        switch (instrumentType) {
        case 'guitar':
          this.$refs.guitarView.show();
          this.$refs.pianoView.hide();
          break;
        case 'piano':
          this.$refs.guitarView.hide()
          this.$refs.pianoView.show();
          break;
        }
      }
    }
  })

</script>

<style>
h1 {
  display: inline;
}

.InstrumentSelector {
  display: inline;
  float: right;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
