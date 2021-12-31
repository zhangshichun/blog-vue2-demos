<template>
<div>
  我们是TI{{ ame }}冠军
  <el-button @click="playDota2(1)">加</el-button>
  <el-button @click="playDota2(-1)">减</el-button>
</div>
</template>
<script>
export default {
  props: {
    ame: {
      type: Number,
      default: 8
    }
  },
  model: {
    prop: 'ame',
    event: 'zard'
  },
  methods: {
    playDota2(step) {
      const newYear = this.ame + step
      this.$emit('zard', newYear)
    }
  }
}
</script>