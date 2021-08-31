<template>
  <div class="block" v-show="showBlock" >
    <h2>Click Me!</h2>
  </div>
</template>

<script>
export default {
  name: 'Block',
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    }
  },

  mounted() {
    this.startTimer()
  },

  methods: {
    startTimer() {
      console.log(this.delay)
      setTimeout(() => {
        this.showBlock = true
      }, this.delay)
    },

    stopTimer() {

    }
  },
}
</script>

<style>
  .block {
    width: 400px;
    cursor: pointer;
    background-color: #0faf87;
    color: white;
    margin: 100px auto;
    padding: 100px 0;
    border-radius: 20px;
  }

  .block:hover {
    opacity: 0.8;
  }
</style>