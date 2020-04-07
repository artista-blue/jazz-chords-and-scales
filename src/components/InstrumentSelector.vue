<template>
  <div>
    <img src='../assets/piano.png' @click="selectHandler('piano')">
    <img src='../assets/guitar.png' @click="selectHandler('guitar')">
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
     name: 'InstrumentSelector',
     props: {
       selectHandler: {
         type: Function
       }
     }
  })
</script>

<style>
  img {
    width: 50px;
    height: 50px;
  }
</style>
