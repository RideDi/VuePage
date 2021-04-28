<template>
  <div id="ParameterSetting">
    <div class="common-layout">
      <el-container>
        <el-header>
          <el-row :gutter="20">
            <el-col><div style="font-size: 20px;">舆情监控参数介绍</div></el-col>
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

</template>

<script>
export default {
  data() {
    return {
      tableData: [{
        parameterName: '属地模式',
        parameterIntroduce: '属地模式即为可以根据输入地点，针对地点的'
      }, {
        parameterName: '全局模式',
        parameterIntroduce: '即对全局进行舆情监测'
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
