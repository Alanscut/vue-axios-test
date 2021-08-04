<template>
  <div id="app">
    <button @click="reset">reset msg</button>
    <button @click="getMsg1">get msg by this.axios</button>
    <button @click="getMsg2">get msg by this.$http</button>
    <button @click="getMsg3">get msg by Vue.axios</button>
    <button @click="getMsg4">get msg by Vue.$http</button>
    <div v-html="msg"></div>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  name: "App",
  data() {
    return {
      msg: "Hello, World!",
    };
  },
  methods: {
    reset() {
      this.msg = "Hello, World!";
    },
    getMsg1() {
      this.axios
        .get("http://localhost:3000/greet")
        .then((res) => (this.msg = res.data));
    },
    getMsg2() {
      this.$http
        .get("http://localhost:3000/greet")
        .then((res) => (this.msg = res.data));
    },
    getMsg3() {
      Vue.axios
        .get("http://localhost:3000/greet")
        .then((res) => (this.msg = res.data));
    },
    getMsg4() {
      Vue.$http
        .get("http://localhost:3000/greet")
        .then((res) => (this.msg = res.data));
    },
  },
};
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
