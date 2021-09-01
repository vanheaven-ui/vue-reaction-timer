<template>
  <p>Reaction Time: {{ score }} ms</p>
  <h3>{{ rank }}</h3>
</template>

<script>
export default {
  name: "Results",
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Trigger fingers 🔫";
    } else if (this.score < 400) {
      this.rank = "Rapid reflexes 💪";
    } else {
      this.rank = "Snail pace... 🐌";
    }
  },
};
</script>

<style>
</style>