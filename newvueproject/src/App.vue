<template>


  <div id="app">

    <navBar></navBar>

    <img alt="Vue logo" src="./assets/logo.png" />

    <HelloWorld msg="Alejo's Vue.js testing ground" />

    <footerMain></footerMain>

  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import navBar from "./components/navBar.vue";
import footerMain from "./components/footerMain.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    footerMain,
    navBar,
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
