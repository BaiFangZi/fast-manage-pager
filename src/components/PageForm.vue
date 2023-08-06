<template>
  <div class="header-form-container">
    <el-form :model="formModel" inline ref="HeaderForm">
      <el-form-item v-for="formItem in formComponents" :prop="formItem.prop">
        <template v-if="!formItem.hidden">
          <component
            :is="formItem.component"
            v-model="formModel[formItem.prop]"
            v-bind="formItem.attrs"
            v-on="formItem.listeners"
          ></component>
        </template>
      </el-form-item>
      <el-form-item>
        <el-button @click="handleQuery">查询</el-button>
        <el-button @click="handleReset">重置</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
import ElSelect from './Select.vue'
export default {
  components: { ElSelect },
  data() {
    return {
      formModel: {
        input: '',
        select: '',
        date: ''
      },
      formComponents: [
        {
          component: 'el-input',
          prop: 'input',
          attrs: {
            value: '',
            placeholder: '请选择活动区域'
          },
          listeners: {
            input: (val) => {
              console.log(val)
            }
          }
        },
        {
          component: 'el-select',
          prop: 'select',
          attrs: {
            value: '',
            clearable: true,
            placeholder: '请选择活动区域',
            options: [
              {
                value: '选项1',
                label: '黄金糕'
              },
              {
                value: '选项2',
                label: '双皮奶'
              },
              {
                value: '选项3',
                label: '蚵仔煎'
              },
              {
                value: '选项4',
                label: '龙须面'
              },
              {
                value: '选项5',
                label: '北京烤鸭'
              }
            ]
          },
          listeners: {
            change: (val) => {
              console.log(val)
            }
          }
        },
        {
          component: 'el-date-picker',
          prop: 'date',
          attrs: {
            value: '',
            placeholder: '请选择时间'
          }
        }
      ]
    }
  },
  methods: {
    handleQuery() {
      console.log(this.formModel)
    },
    handleReset() {
      this.$refs.HeaderForm.resetFields()
    }
  }
}
</script>

<style lang="scss" scoped>
.header-form-container {
  // display: flex;
  // align-items: center;
  // justify-content: space-between;
  ::v-deep .el-form {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 60px;
    .el-form-item {
      margin: 0;
    }
  }
}
</style>
