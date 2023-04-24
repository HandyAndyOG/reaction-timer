<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    <h2 class="content">Click me!</h2>
  </div>
</template>
<script>
export default {
  props: {
    delay: Number,
  },
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
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10);
    },
    stopTimer() {
        clearInterval(this.timer)
        this.$emit('end', this.reactionTime)
    },
  },
};
</script>

<style scoped>
.block {
  display: flex;
  justify-content: center;
  align-items: center;
  background: green;
  width: 400px;
  height: 200px;
  margin: 30px;
  border-radius: 5px;
}
.content {
  color: white;
}
</style>
