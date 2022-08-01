<template>
  <div>
    <XLProgress
      percentage="10"
      color="red"
      type="round"
      boxHeight="5"
      boxWidth="300"
    ></XLProgress>

    <XLProgress percentage="60" color="#000" type="round"></XLProgress>
   
    <XLProgress percentage="80"></XLProgress>
    
    <!-- 圆形进度条 -----未完成------ -->
    <XLcircleProgress percentage="90"></XLcircleProgress>
  </div>
</template>

<script>
import XLProgress from "@/components/progress.vue"
import XLcircleProgress from "@/components/circleProgress.vue"
export default {
  components: {
    XLProgress,
    XLcircleProgress,
  },
}
</script>

<style scoped lang="less"></style>
