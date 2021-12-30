<template>
  <h1>Ninja Reaction Timer</h1>
  <!-- 'disabled' refers to the HTML property, it's nothing unique from Vue -->
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <p v-if="showResults">Reaction time: {{ score }} ms</p>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
      // An amount time between 1s and 4s
      this.delay = 1000 + (Math.random() * 3000)
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
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
