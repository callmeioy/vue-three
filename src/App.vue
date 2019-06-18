<template>
  <div id="app">
    <h1>
      <a href="http://www.ioyweb.com" target="_blank">{{title}}</a>
    </h1>
    <Threemap></Threemap>
  </div>
</template>

<script>
import Threemap from "./components/Threemap";

export default {
  data() {
    return {
      title: "ioyweb.com -- vue-three"
    };
  },
  name: "App",
  components: {
    Threemap
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
