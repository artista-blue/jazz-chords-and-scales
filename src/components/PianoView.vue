<template>
  <div v-if='seen'>
    <h1>Piano View</h1>

    <div class='housing'>
    <div style="clear: both; display: block;">

      <div id="upperKeys">
	<component v-for="item in upperKeys" v-bind:is="item.type" :params="item" :key="item.key"></component>	
      </div>
      <div style='clear: both;'></div>
      <div id="lowerKeys">
	<component v-for="item in lowerKeys" v-bind:is="item.type" :params="item" :key="item.key"></component>
      </div>

    </div>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import PianoKey from './PianoKey.vue'

  export default Vue.extend ({
    name: 'PianoView',
    components: {
      PianoKey
    },
    data () {
      const upperKeys = [
        {type: 'PianoKey', note: 'C', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Db', octave: 3, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'D', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Eb', octave: 3, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'E', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'F', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Gb', octave: 3, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'G', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Ab', octave: 3, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'A', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Bb', octave: 3, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'B', octave: 3, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'C', octave: 4, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Db', octave: 4, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'D', octave: 4, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Eb', octave: 4, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'E', octave: 4, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'F', octave: 4, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Gb', octave: 4, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'G', octave: 4, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Ab', octave: 4, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'A', octave: 4, showLabel: false, isLower: false},
        {type: 'PianoKey', note: 'Bb', octave: 4, showLabel: true, isLower: false},
        {type: 'PianoKey', note: 'B', octave: 4, showLabel: false, isLower: false},
      ];
      const lowerKeys = [
        {type: 'PianoKey', note: 'C', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'D', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'E', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'F', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'G', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'A', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'B', octave: 3, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'C', octave: 4, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'D', octave: 4, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'E', octave: 4, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'F', octave: 4, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'G', octave: 4, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'A', octave: 4, showLabel: true, isLower: true},
        {type: 'PianoKey', note: 'B', octave: 4, showLabel: true, isLower: true},
      ];
      return {
        seen: false,
        upperKeys: upperKeys,
        lowerKeys: lowerKeys
      }
    },
    methods: {
      show () {
        this.seen = true;
/**
        console.log(this);
        console.log(this.$children);
        console.log(this.$children[0]);
        console.log(this.$children[0].params);
        this.$children[0].params.note = 'R';
        console.log(this.$children[0].params.degree);
**/
      },
      hide () {
       this.seen = false
      }
    }
  })
</script>

<style>
  .w1 {
      width: 22px;
      height: 200px;
      border-top: 1px solid #abb2b7;
      float: left;
  }
  .w2 {
      width: 40px;
      height: 200px;
      border-top: 1px solid #abb2b7;
      border-left: 1px solid #abb2b7;
      border-right: 1px solid #abb2b7;
      float: left;
  }
  .w3 {
      width: 60px;
      height: 130px;
      border-left: 1px solid #abb2b7;
      border-right: 1px solid #abb2b7;
      border-bottom: 1px solid #abb2b7;
      float: left;
  }
  .b {
      width: 40px;
      height: 200px;
      border-top: 1px solid #abb2b7;
      background-color: black;
      float: left;
      color: white;
  }
  .housing {
      padding: 10px;
      height: 400px;
  }
</style>
