<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start">Play</button>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      // An amount time between 1s and 4s
      this.delay = 1000 + (Math.random() * 3000)
      this.isPlaying = true
      console.log(this.delay)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
