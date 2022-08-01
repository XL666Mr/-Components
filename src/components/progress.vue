<template>
  <div class="progress">
    <!-- 进度条 -->
    <div
      class="Progress_out"
      :class="type"
      :style="{ height: boxHeight + 'px', width: boxWidth + 'px' }"
    >
      <div
        class="Progress_inside circle_left ab"
        :style="{ width: percentage + '%', backgroundColor: color }"
      ></div>
    </div>
    <!-- 外部提示 -->
    <span v-if="percentage < 100">{{ percentage + "%" }}</span>
    <span v-else-if="(percentage = 100)">正好</span>
    <span v-else-if="percentage > 100">满了满了</span>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  props: {
    percentage: {
      type: String,
      default: "50",
    },
    color: {
      type: String,
      default: "green",
    },
    type: {
      type: String,
      default: "",
    },
    boxWidth: {
      type: String,
      default: "200",
    },
    boxHeight: {
      type: String,
      default: "20",
    },
  },
}
</script>

<style scoped lang="less">
.Progress_out {
  border: 1px solid;
  margin: 10px;
  overflow: hidden;
  .Progress_inside {
    height: 100%;
    background-color: red;
    color: aliceblue;
    text-align: center;
  }
}
.round {
  border-radius: 15px;
}

.progress {
  display: flex;
  align-items: center;
}
</style>
