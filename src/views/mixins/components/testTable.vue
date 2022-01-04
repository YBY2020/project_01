<template>
  <el-table
    :data="list"
    border
    style="width: 100%;"
  >
    <el-table-column
      prop="nick"
      label="昵称"
      width="180"
    />
    <el-table-column
      prop="phone"
      label="手机号"
      width="180"
    />
    <el-table-column
      prop="name"
      label="姓名"
      width="180"
    />
    <el-table-column
      prop="subject"
      label="所属学科"
    />
    <el-table-column
      prop="job"
      label="职位"
    />
    <el-table-column
      prop="year"
      label="工作年限"
    />
    <el-table-column
      prop="updataTime"
      label="录入时间"
    />
    <el-table-column
      label="操作"
    >
      <el-button type="danger">删除</el-button>
    </el-table-column>
  </el-table>
</template>

<script>
export default {
  props: {
    list: {
      type: Array,
      default() {
        return []
      }
    }
  }
}
</script>

<style lang="scss">
.el-table--border th, .el-table--border td {
  text-align: center;
}
</style>
