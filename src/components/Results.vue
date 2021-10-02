<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="rank" v-html="rank"></p>
  <p class="mini-desc" v-html="rankDesc"></p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
      rankDesc: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Cheetah Pace 🐆: Wow, you're fast!";
      this.rankDesc = "You've got a pig for dinner. Yummm";
    } else if (this.score < 400) {
      this.rank = "Cat Pace 🐈: Rapid reflex";
      this.rankDesc = "You've got a fish. Yay!";
    } else if (this.score < 600) {
      this.rank = "Snail Pace 🐌: Too slow...";
      this.rankDesc = "No wonder you can only eat leaves";
    } else {
      this.rank = "Stone Pace 🗿: did you even move?";
      this.rankDesc = "Wind is all you've got... for meal";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: #4fc08d;
  font-weight: bold;
  margin-top: 1.6rem;
  margin-bottom: 1rem;
}

.mini-desc {
  font-size: 1rem;
  color: #2c3e50;
  font-weight: bold;
}
</style>
