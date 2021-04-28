<template xmlns:el-col="http://www.w3.org/1999/html">
  <el-row type="flex" justify="center">
    <el-col :span="8"><el-button type="primary" icon="el-icon-delete">删除选中</el-button></el-col>
    <el-col :span="8" ><el-button type="primary" icon="el-icon-circle-plus-outline">新建任务</el-button></el-col>
  </el-row>
  <el-container style="height: 500px; border: 1px solid #eee">
    <!--    <el-container>-->
    <el-header style="text-align: left; font-size: 20px">
      <el-row :gutter="20">
        <el-col :span="3">
          <span>社群爬取</span>
        </el-col>
        <!--        <el-button type="primary" icon="el-icon-circle-plus-outline">新建任务</el-button>-->
        <el-col :offset="14" :span="2">
          <span>搜索</span>
        </el-col>
        <el-col :span="5">
          <span
              style="width:40%;text-align:right"><el-input
              placeholder="请输入内容"
              v-model="input"
              clearable>
            </el-input></span>
        </el-col>
      </el-row>
    </el-header>

    <el-main>
      <el-table :data="tableData" border style="width: 100%" ref="multipleTable" tooltip-effect="dark" @selection-change="handleSelectionChange" >
        <el-table-column type="selection" width="55"></el-table-column>
        <el-table-column prop="id" label="id" width="140">
        </el-table-column>
        <el-table-column prop="name" label="用户名" width="120">
        </el-table-column>
        <el-table-column prop="na" label="用户昵称" width="120">
        </el-table-column>
        <el-table-column prop="state" label="状态" width="120">
          <el-tag type="success">互相关注</el-tag>
        </el-table-column>
        <el-table-column prop="operation" label="操作" width="220">
          <template #default="scope">
            <el-button size="mini" @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
            <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
    </el-main>
  </el-container>
  <!--  </el-container>-->
</template>

<script>
export default {
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      na: 'xiaohu',
      address: '上海市普陀区金沙江路 1518 弄',
      id: 10000,
      state: '已完成'
    };
    return {
      tableData: Array(20).fill(item),
      multipleSelection: []
    }
  },
  methods: {
    handleEdit(index, row) {
      console.log(index,row);
    },
    handleDelete(index, row) {
      console.log(index, row);
    },
    fileterTag(value, row) {
      return row.tag === value;
    },
    toggleSelection(rows) {
      if (rows) {
        rows.forEach(row => {
          this.$refs.multipleTable.toggleRowSelection(row);
        });
      } else {
        this.$refs.multipleTable.clearSelection();
      }
    },
    handleSelectionChange(val) {
      this.multipleSelection = val;
    }
  }
};
</script>

<style>
.el-header {
  background-color: #B3C0D1;
  color: #333;
  line-height: 60px;
}

.el-aside {
  color: #333;
}
.el-input {
  width:120px;
  text-align: center;

}
</style>
