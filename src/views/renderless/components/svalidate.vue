<template>
  <div>
    <slot :validate="validate" />
    <el-alert :title="errMsg" type="warning" />
  </div>
</template>

<script>
export default {
  props: ['value', 'rules'],
  data() {
    return {
      errMsg: ''
    }
  },
  methods: {
    validate() {
      const validate = this.rules.reduce((pre, cur) => {
        const check = cur && cur.test && cur.test(this.value)
        this.errMsg = check ? '' : cur.errMsg
        return pre && check
      }, true)
      return validate
    }
  }
}
</script>

<style lang="scss" scoped>
.el-alert--warning.is-light {
  background-color: #fff;
}
</style>
