<template>
  <div id="app">
    <MainWrapper />
  </div>
</template>

<script>
import MainWrapper from "./components/MainWrapper";
export default {
  name: "App",
  components: {
    MainWrapper,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.np-app-title {
  text-align: center;
  width: 200px;
}
.np-app-container {
  width: 210px;
  height: 395px;
  margin: 0 auto;
  margin-top: 10px;
  background: #fff;
  border-radius: 10px;
  padding: 12px;
}
</style>
