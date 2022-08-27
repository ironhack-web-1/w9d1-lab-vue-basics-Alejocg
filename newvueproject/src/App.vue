/* eslint-disable */

<template>


  <div id="app">

    <navBar></navBar>

    <img alt="Vue logo" src="./assets/logo.png" />

    <HelloWorld msg="Alejo's Vue.js testing ground!" />
    

    <formMain></formMain>

    <footerMain></footerMain>
    

  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import navBar from "./components/navBar.vue";
import footerMain from "./components/footerMain.vue";
import formMain from "./components/formMain.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    footerMain,
    navBar,
    formMain,
    
  },
};
</script>



<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  align-items: center;

  
}

</style>
