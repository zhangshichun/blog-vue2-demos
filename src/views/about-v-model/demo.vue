<template>
  <div>
    <div>
      <h3>副作用: 新增响应式属性</h3>
      <el-input v-model="user.tel"></el-input>
      <div>user.tel: {{ user.tel }}</div>      
    </div>
    <div>
      <h3>原生组件的等价</h3>
      <div>
        <label>Textarea</label>
        <textarea v-model="valueOfText" />
        <!-- eslint-disable-next-line vue/no-textarea-mustache -->
        <textarea @input="valueOfText = $event.target.value" > {{ valueOfText }}</textarea>
      </div>
      <div>
        <label>Select</label>
        <select v-model="valueOfSelect">
          <option value="0">上</option>
          <option value="1">下</option>
        </select>
        <select :value="valueOfSelect" @change="valueOfSelect = $event.target.value">
          <option value="0">上</option>
          <option value="1">下</option>
        </select>        
      </div>
      <div>
        <label>Radio</label>
        <input name="test" type="radio" value="1" v-model="valueOfRadio" /> 
        <input name="test" type="radio" value="2" v-model="valueOfRadio" /> 

        <input name="test2" type="radio" value="1" :checked="valueOfRadio == '1'" @change="valueOfRadio = $event.target.value"/> 
        <input name="test2" type="radio" value="2" :checked="valueOfRadio == '2'" @change="valueOfRadio = $event.target.value"/> 

      </div>
      <div>
        <label>Checkbox: {{valueOfCheckbox}}</label>
        <input name="test" type="checkbox" value="1" v-model="valueOfCheckbox" /> 
        <input name="test" type="checkbox" value="2" v-model="valueOfCheckbox" /> 

        <input name="test2" type="checkbox" value="1" :checked="valueOfCheckbox.includes('1')" @change="onChecked"/> 
        <input name="test2" type="checkbox" value="2" :checked="valueOfCheckbox.includes('2')" @change="onChecked"/>
      </div>
    </div>
    <div>
      <h3>自定义的 v-model</h3>
      <dota v-model="ti"></dota>
    </div>
  </div>
</template>
<script>
import Dota from './dota.vue'
export default {
  components: {
    Dota
  },
  data() {
    return {
      user: {
        name: '公众号: 前端要摸鱼',
      },
      valueOfText: 'text',
      valueOfSelect: '1',
      valueOfRadio: null,
      valueOfCheckbox: [],
      ti: 8
    }
  },
  methods: {
    onChecked (event) {
      const checked = event.target.checked
      const value = event.target.value
      const index = this.valueOfCheckbox.indexOf(value)
      if (checked && index == -1) {
        this.valueOfCheckbox.push(value)
      } else {
        this.valueOfCheckbox.splice(index, 1)
      }
    }
  }
}
</script>