<template>
  <div id="app">
    <PageForm />
    <PageTable :data="tableData" :columns="columns">
      <template #date>
        <TableColumn name="date" label="日期" v-slot="scope">{{
          scope.row.date
        }}</TableColumn>
      </template>
      <template #city>
        <TableColumn name="city" label="区域" v-slot="scope">区域是{{
          scope.row.city
        }}</TableColumn>
      </template>
    </PageTable>
  </div>
</template>

<script>
import PageForm from './components/PageForm.vue'
import PageTable from './components/PageTable.vue'
import TableColumn from './components/TableColumn.vue'
export default {
  name: 'App',
  components: {
    PageForm,
    PageTable,
    TableColumn
  },
  data() {
    return {
      tableData: [
        {
          date: '2016-05-03',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        },
        {
          date: '2016-05-02',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        },
        {
          date: '2016-05-04',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        },
        {
          date: '2016-05-01',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        },
        {
          date: '2016-05-08',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        },
        {
          date: '2016-05-06',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        },
        {
          date: '2016-05-07',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }
      ],
      columns: [
        // date: '2016-05-01',
        //     name: '王小虎',
        //     province: '上海',
        //     city: '普陀区',
        //     address: '上海市普陀区金沙江路 1518 弄',
        //     zip: 200333
        {
          prop: 'date',
          slot: 'date',
          label: '日期'
        },
        {
          prop: 'name',
          label: '姓名'
          // slot: 'date'
        },
        {
          prop: 'province',
          label: '省份'
          // slot: 'date'
        },
        {
          prop: 'city',
          label: '区域',
          slot: 'city'
        },
        {
          prop: 'address',
          label: '详细地址'
          // slot: 'date'
        },
        {
          prop: 'zip',
          label: '邮编'
          // slot: 'date'
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
