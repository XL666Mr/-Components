<template>
  <div class="circle">
    <div class="circle_left ab" :style="deg"></div>
    <div class="circle_right ab" :style="deg1"></div>
    <div class="circle_text">
      <span class="value" v-if="percentage <= 100">{{ percentage }}%</span>
      <span class="value" v-else>满了</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    percentage: {
      type: String,
      default: "98",
    },
  },
  computed: {
    deg() {
      if (this.percentage >= 50) {
        return "transform: rotate(" + 3.6 * this.percentage + "deg);"
      } else {
        return 
      }
    },
    // 未完成
    deg1() {
      if (this.percentage < 50) {
        return "transform: rotate(" + 3.6 * this.percentage + "deg);"
      } else {
        return
      }
    },
  },
}
</script>

<style scoped lang="less">
.circle {
  width: 80px;
  height: 80px;
  position: relative;
  border-radius: 50%;
  left: 200px;
  top: 50px;
  box-shadow: inset 0 0 0 5px #ccc;

  .ab {
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    margin: auto;
  }

  &_left {
    border: 5px solid #546063;
    border-radius: 50%;
    clip: rect(0, 40px, 80px, 0);
  }

  &_right {
    border: 5px solid #546063;
    border-radius: 50%;
    clip: rect(0, 80px, 80px, 40px);
  }
  &_text {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #000;
  }
}
</style>
