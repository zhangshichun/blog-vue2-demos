<template>
  <div class="like-a-page">
    <FullScreen class="like-a-module" ref="my-full-screen">
      <el-button @click="requestOwnFullScreen">我封装的全屏</el-button>
      <el-select>
        <el-option>随便写点啥</el-option>
      </el-select>
    </FullScreen>
    <div class="like-a-module" ref="browser-full-screen">
      <el-button @click="requestBrowserFullScreen">官方的全屏</el-button>
      <el-select>
        <el-option>随便写点啥</el-option>
      </el-select>
    </div>
  </div>
</template>
<script>
import FullScreen from './full-screen.vue'
export default {
  components: {
    FullScreen
  },
  methods: {
    requestBrowserFullScreen() {
      this.$refs['browser-full-screen'].requestFullscreen()
    },
    requestOwnFullScreen() {
      this.$refs['my-full-screen'].request()
    }
  }
}

</script>
<style lang="css">
.like-a-page {
  width: 800px;
  height: 600px;
  background-color: #e5e5e5;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}
.like-a-module{
  width: 400px;
  height: 200px;
  background-color: white;
}
</style>