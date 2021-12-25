<template>
<div>
  <Picker v-model="show"></Picker>
  <div>这是一些文本</div>
</div>
</template>
<script>
import Picker from './picker.vue'
export default {
  components: {
    Picker
  },
  data() {
    return {
      show: false
    }
  }
}
</script>