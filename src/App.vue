<template>
  <h1>{{ title }} ⏱️</h1>
  <button @click="start">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <p v-show="showScore">Reaction Time: {{ score }} ms</p>
</template>

<script>
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: { Block },
  data() {
    return {
      title: "Vanheaven Reaction Timer",
      isPlaying: false,
      delay: null,
      score: null,
      showScore: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showScore = false;
    },

    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showScore = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  cursor: pointer;
}
</style>
