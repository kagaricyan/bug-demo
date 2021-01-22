<template>
  <div class="ant-table-demo">
    <a-table row-key="name" :data-source="dataList">
      <a-table-column title="国家" data-index="country" :custom-render="mergeCountry"/>
      <a-table-column title="姓名" data-index="name"/>
      <template #expandedRowRender="record">
        <span><b>年龄: </b>{{record.age}}</span> <br>
        <span><b>性别: </b>{{record.gender}}</span>
      </template>
    </a-table>
  </div>
</template>

<script>
import {defineComponent} from '@vue/composition-api';

export default defineComponent({
  name: 'ant-table-demo',
  setup() {
    const dataList = [
      { country: '中国', name: '张三', age: 12, gender: '男', show: true, rowSpan: 3 },
      { country: '中国', name: '李四', age: 13, gender: '女' },
      { country: '中国', name: '王五', age: 14, gender: '男' },
    ]

    function mergeCountry(value, row) {
      const obj = {
        children: value,
        attrs: {},
      };
      if (row.show === true) {
        obj.attrs.rowSpan = row.rowSpan;
      } else {
        obj.attrs.rowSpan = 0;
      }
      return obj;
    }

    return {
      dataList,
      mergeCountry
    }
  }
})
</script>


<style scoped>
  .ant-table-demo{
    width: 50%;
    height: 50%;
    margin: 100px auto;
  }
</style>
