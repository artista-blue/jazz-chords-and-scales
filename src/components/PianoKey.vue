<template>
  <div :style='classObject'>
    <div class='label' v-if='params.showLabel'>{{label}}</div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';

  export default Vue.extend({
    name: 'PianoKey',
    props: ['params'],
    computed: {
      label () {
        if (!this.params) {
          return ''
        }
        if (this.params.degree) {
          return `${this.params.note}(${this.params.degree})`;
        }
        return `${this.params.note}`;
      },
      classObject () {
        if (this.params.isLower === true) {
          return { // w3
            width: '60px',
            height: '130px',
            'border-left': '1px solid #abb2b7',
            'border-right': '1px solid #abb2b7',
            'border-bottom': '1px solid #abb2b7',
            float: 'left'
          };
        }
        const whiteKeys = ['C', 'D', 'E', 'F', 'G', 'A', 'B'];
        if (!whiteKeys.includes(this.params.note)) {
          return {
            width: '40px',
            height: '200px',
            'border-top': '1px solid #abb2b7',
            'background-color': 'black',
            'float': 'left',
            'color': 'white'
          };
        }
        const w2Keys = ['D', 'G', 'A']
        if (!w2Keys.includes(this.params.note)) {
          return {  // w2
            width: '40px',
            height: '200px',
            'border-top': '1px solid #abb2b7',
            'border-left': '1px solid #abb2b7',
            'border-right': '1px solid #abb2b7',
            'float': 'left'
          };
        }
        return {  // w1
          'width': '22px',
          'height': '200px',
          'border-top': '1px solid #abb2b7',
          'float': 'left'
        };
      }
    }
  })
</script>

<style>
  .w3 {
    width: 60px;
    height: 130px;
    border-left: 1px solid #abb2b7;
    border-right: 1px solid #abb2b7;
    border-bottom: 1px solid #abb2b7;
    float: left;
  }
  .label {
    width:100px;
    height:70px;
    display:table-cell;
    text-align:center;
    vertical-align:bottom;
    margin:10px;
  }
</style>
