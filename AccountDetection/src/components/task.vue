<template>
  <div id="ParameterSetting">
    <div class="common-layout">
      <el-container>
        <el-header>
          <el-row :gutter="20">
            <el-col><div style="font-size: 20px;">用户检测参数介绍</div></el-col>
          </el-row>
        </el-header>
      </el-container>
    </div>
  </div>
  <el-table
      :data="tableData"
      border
      style="width: 100%">
    <el-table-column
        prop="parameterName"
        label="参数名"
        width="500%">
    </el-table-column>
    <el-table-column
        prop="parameterIntroduce"
        label="参数属性"
        width="500%">
    </el-table-column>
  </el-table>
  <el-row type="flex" justify="center">
    <el-col :span="8" ><el-button type="primary" icon="el-icon-circle-plus-outline">新建任务</el-button></el-col>
  </el-row>
</template>

<script>
export default {
  data() {
    return {
      tableData: [{
        parameterName: '用户名',
        parameterIntroduce: '输入需要进行检测的用户名'
      }, {
        parameterName: '时间戳',
        parameterIntroduce: '设置时间戳可以对这段时间的舆情进行监控'
      }]
    }
  }
}
</script>

<style>

</style>
