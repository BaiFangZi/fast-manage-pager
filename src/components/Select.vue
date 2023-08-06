<template>
  <div>
    <el-select v-bind="$attrs" v-on="$listeners">
      <el-option
        v-for="op in $attrs.options"
        :label="op.label"
        :value="op.value"
        :key="op.value"
      ></el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  props: {},
  // watch: {
  //   value: {
  //     handler(val) {
  //       console.log(val)
  //     }
  //   }
  // },
  data() {
    return {}
  },
  created() {
    console.log(this)
  }
}
</script>
