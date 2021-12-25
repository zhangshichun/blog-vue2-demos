<template>
<div class="about-append-to-body">
  <div class="container">
    <el-date-picker
      v-model="value"
      type="date"
      placeholder="选择日期">
    </el-date-picker>
  </div>
  <div class="container">
    <el-date-picker
      v-model="value"
      type="date"
      placeholder="选择日期"
      :append-to-body="false"
      >
    </el-date-picker>
  </div>
</div>
</template>
<script>
export default {
  data() {
    return {
      value: null
    }
  }
}
</script>
<style>
.about-append-to-body {
  display: flex;
  flex-direction: row;
}
.about-append-to-body .container {
  width: 400px;
  position: relative;
  overflow: auto;
}
</style>
