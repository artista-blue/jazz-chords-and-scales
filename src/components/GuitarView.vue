<template>
  <div v-if='seen'>
    <h1>Guitar View</h1>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend ({
    data () {
      return {
        seen: false
      }
    },
    methods: {
      show () {
        this.seen = true;
      },
      hide () {
       this.seen = false
      }
    }
  })
</script>

<style>
</style>
