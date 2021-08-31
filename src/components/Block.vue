<template>
  <div class="block" v-show="showBlock" @click="stopTimer">
    <h2>Click Me!</h2>
  </div>
</template>

<script>
export default {
  name: "Block",
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },

  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
      this.$emit("hide");
    }, this.delay);
  },

  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },

    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime);
      console.log(this.reactionTime);
    },
  },
};
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