<template>
  <div id="app">
    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="是否append-to-body" name="AboutAppendToBody"></el-tab-pane>
      <el-tab-pane label="Picker实战" name="MyPicker"></el-tab-pane>
      <el-tab-pane label="PopupManager" name="PopupManager"></el-tab-pane>
      <el-tab-pane label="全屏组件" name="FullScreen"></el-tab-pane>
    </el-tabs>
    <component :is="activeName"></component>
  </div>
</template>

<script>
import MyPicker from './views/my-picker'
import AboutAppendToBody from './views/about-append-to-body'
import PopupManager from './views/popup-manager'
import FullScreen from './views/full-screen/demo.vue'
export default {
  name: 'app',
  data() {
    return {
      activeName: 'PopupManager'
    }
  },
  components: {
    MyPicker,
    AboutAppendToBody,
    PopupManager,
    FullScreen
  }
}
</script>
