<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="first vue   docker部署测试" />
    <h1>测试vue提交后触发jenkins自动部署</h1>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import axios from "axios";
export default {
  name: "app",
  components: {
    HelloWorld
  },
  created() {
    this.getData();
  },
  methods: {
    async getData() {
      let res = await axios({
        method: "get",
        url: "http://dev.ksc009.cn:3009/api/users"
      });
      // eslint-disable-next-line
      console.log(res)
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
