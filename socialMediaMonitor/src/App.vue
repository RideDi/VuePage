<template>
  <img class="logo" alt="Vue logo" src="./assets/logo.png">
  <HelloWorld :msg="msg"/>
<!--  <monitorModel/>-->
  <historicalTask/>
<!--  <taskParameters/>-->
<!--  <historicalUserTesting/>-->
  <div class="btn">
    <el-button type="primary" @click="startHacking">
      Get Started
    </el-button>
  </div>
</template>

<script>
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
// import monitorModel from "@/components/monitorModel";
import historicalTask from "../../element-plus-starter/src/components/historicalUserTesting";
// import taskParameters from "@/components/taskParameters";
// import historicalUserTesting from "@/components/historicalUserTesting";
export default {
  name: 'App',
  components: {
    // taskParameters,
    historicalTask,
    // monitorModel,
    HelloWorld,
    // historicalUserTesting
  },
  setup() {
    const msg = ref("Welcome to Element Plus, a Vue 3.0 based component library")
    const startHacking = () => {
      msg.value = "Start coding with Element Plus with 💖"
    }
    return {
      msg,
      startHacking
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
.logo {
  width: 50%;
}
.btn {
  margin-top: 100px;
}
</style>
