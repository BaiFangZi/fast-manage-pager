<template>
  <el-table-column :prop="name" :label="label">
    <template slot-scope="scope">
      <slot :row="scope.row"></slot>
    </template>
  </el-table-column>
</template>
<script>
export default {
  props: ['name', 'label'],
  created() {
    console.log(this)
  }
}
</script>
