<template>
  <div class="page-table-container">
    <el-table class="page-table-main" :data="data">
      <!-- <el-table-column v-for="column in columns">
      <template v-if="column.slot">
        <div>
          
        </div>
      </template>
      <v-else></v-else>
      </el-table-column> -->
      <template v-for="column in columns">
        <el-table-column
          v-if="!column.slot"
          :prop="column.prop"
          :label="column.label"
        ></el-table-column>
        <slot v-else :name="column.slot"> </slot>
      </template>
    </el-table>
    <div class="page-table-footer"></div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      require: true,
      type: Array,
      default: () => []
    },
    columns: {
      require: true,
      type: Array,
      default: () => []
    }
  }
}
</script>
