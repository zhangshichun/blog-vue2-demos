<template>
  <div>
    <el-button @click="onClick">增加</el-button>
    z-index: {{ value }} </div>
</template>
<script>
import { PopupManager } from 'element-ui/src/utils/popup'
export default {
  data() {
    return {
      value: 0
    }
  },
  methods: {
    onClick() {
      // 没错，使用起来就是这么简单，只要一行
      this.value = PopupManager.nextZIndex()
    }
  }
}
</script>