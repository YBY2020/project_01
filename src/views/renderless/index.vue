<template>
  <div>
    <s-validate #default="{ validate }" :value="value" :rules="[rules[0]]">
      <el-input v-model="value" @blur="validate" />
    </s-validate>
    <s-validate #default="{ validate }" :value="valueTextarea" :rules="[rules[1]]">
      <el-input v-model="valueTextarea" type="textarea" @blur="validate" />
    </s-validate>
  </div>
</template>

<script>
import SValidate from './components/svalidate.vue'
export default {
  name: 'Rederless',
  components: { SValidate },
  data() {
    return {
      value: '',
      valueTextarea: '',
      rules: [
        {
          test(value) {
            return /\d+/.test(value)
          },
          errMsg: '至少输入一个数字'
        },
        {
          test(value) {
            return /^[a-zA-Z0-9_-]{6,18}$/.test(value)
          },
          errMsg: '请输入6-18位不包含特殊字符的字母或数字或_-的组合'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
