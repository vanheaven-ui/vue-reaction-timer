<template>
  <h3 v-show="alert">😂 Wait a minute</h3>
  <h1>{{ title }} ⏱️</h1>
  <button @click="start">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" @hide="hideAlert" />
  <Results v-show="showScore" :score="score" />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";

export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      title: "Vanheaven Reaction Timer",
      isPlaying: false,
      delay: null,
      score: null,
      showScore: false,
      alert: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showScore = false;
      this.alert = true;
    },

    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showScore = true;
    },

    hideAlert() {
      this.alert = false;
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
