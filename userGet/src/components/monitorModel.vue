<template>
  <!--  <img class="logo" alt="Vue logo" src="./assets/logo.png">-->
  <div id="ParameterSetting">
    <div class="common-layout">
      <el-container>
        <el-header>
          <!--          舆情监控任务参数设置-->
          <el-row :gutter="20">
            <el-col><div style="font-size: 20px;">舆情监控模式选择</div></el-col>
          </el-row>
        </el-header>
        <el-main>
          <el-form ref="form" :model="formLabelAlign" size="small" label-width="100px;" :label-position="labelPosition">
<!--            <el-row :gutter="20">-->

<!--              <el-col :span="10">-->
<!--                <el-form-item label="属地">-->
<!--                  <el-input v-model="formLabelAlign.name" placeholder="输入需要爬取的属地"></el-input>-->
<!--                </el-form-item>-->
<!--              </el-col>-->
<!--              <el-col :span="6" :offset="2">-->
<!--                <el-form-item label="模式选择">-->
<!--                  <el-select v-model="formLabelAlign.region" placeholder="请选择爬取模式">-->
<!--                    <el-option label="属地模式" value="user"></el-option>-->
<!--                    <el-option label="全局模式" value="group"></el-option>-->
<!--                  </el-select>-->
<!--                </el-form-item>-->
<!--              </el-col>-->
<!--            </el-row>-->
            <el-row :gutter="20">
              <el-col :span="7" :offset="7">
                <el-form-item label="模式选择">
                  <el-select v-model="formLabelAlign.region" placeholder="请选择爬取模式">
                    <el-option label="用户模式" value="user"></el-option>
                    <el-option label="社群模式" value="group"></el-option>
                  </el-select>
                </el-form-item>
              </el-col>
              <el-col :span="7">
                <el-form-item label="属地">
                  <el-input v-model="formLabelAlign.name" placeholder="输入需要爬取的属地"></el-input>
                </el-form-item>
              </el-col>
            </el-row>
            <el-row :gutter="10">
              <el-col :offset="7">
                <el-form-item label="时间戳设置">
                  <el-col >
                    <el-date-picker type="date" placeholder="选择开始日期" v-model="formLabelAlign.date1" style="width: 80%;"></el-date-picker>
                  </el-col>
                  <el-col class="line" :span="1">-</el-col>
                  <el-col >
                    <el-date-picker type="date" placeholder="选择截止日期" v-model="formLabelAlign.date2" style="width: 9 %;"></el-date-picker>
                  </el-col>
                </el-form-item>
              </el-col>
            </el-row>
            <el-form-item>
              <el-button type="primary" @click="onSubmit">立即创建</el-button>
              <el-button type="">取消</el-button>
            </el-form-item>
          </el-form>
        </el-main>
      </el-container>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      labelPosition: 'left',
      formLabelAlign: {
        name: '',
        region: '',
        date1: '',
        date2: ''
      }
    }
  },
  methods: {
    onSubmit() {
      console.log('submit!');
    }
  }
}
</script>

<style>
.el-header, .el-footer {
  background-color: #B3C0D1;
  color: #333;
  text-align: center;
  line-height: 60px;
}


.el-main {
  background-color: #E9EEF3;
  color: #333;
  text-align: center;
  line-height: 30px;
}

body > .el-container {
  margin-bottom: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.logo {
  width: 50%;
}

</style>
