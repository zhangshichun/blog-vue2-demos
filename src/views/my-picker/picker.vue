<template>
  <div class="my-picker">
    <el-button @click="onClick">弹出</el-button>
    <Popper ref="popper" v-model="showPopper">
    </Popper>
    <div ref="fly-piece" v-show="showPopper" class="my-picker__popper">3333</div>
  </div>
</template>
<script>
import Popper from 'element-ui/src/utils/vue-popper';
Popper.render = (h) => h(null)

export default {
  components: {
    Popper
  },
  data() {
    return {
      showPopper: false
    }
  },
  methods: {
    onClick() {
      this.showPopper = !this.showPopper
    }
  },
  mounted() {
    this.$refs.popper.popperElm = this.$refs['fly-piece'];
    this.$refs.popper.referenceElm = this.$el;
  }
}
</script>
<style>
.my-picker {
  width: 200px;
}
.my-picker__popper {
  width: 200px;
  height: 200px;
  background-color: red;
}
</style>