<template>
  <div class="block" v-if="showBlock" @click.prevent="stopTimer">Click Me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    // console.log("mounted");
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
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
      console.log(this.reactionTime);
      this.$emit("end", this.reactionTime);
    },
  },
};
</script>

<style>
.block {
  width: 90%;
  max-width: 400px;
  border-radius: 20px;
  background: #4fc08d;
  color: white;
  text-align: center;
  padding: 2rem 1rem;
  margin: 2rem auto;
}
</style>
