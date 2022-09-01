/* eslint-disable */

<template>
  <div id="app">
    <navBar></navBar>

    <img alt="Vue logo" src="./assets/logo.png" />

    <HelloWorld msg="Alejo's Vue.js testing ground!" />

    <div>
      <form @submit.prevent="submit" action="submit.php">
        <InputText v-model="name" placeholder="name" />
        <InputText v-model="email" placeholder="email" type="email" />
      </form>

      <div>
        <h3>The parent:</h3>
        <div>Name: {{ name }}</div>
        <div>email: {{ email }}</div>
      </div>
    </div>

    <formMain></formMain>

    <footerMain></footerMain>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import navBar from "./components/navBar.vue";
import footerMain from "./components/footerMain.vue";
import formMain from "./components/formMain.vue";
import InputText from "./components/InputText.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    footerMain,
    navBar,
    formMain,
    InputText,
  },
  data() {
    return {
      name: "",
      email: "email",
      aboutMe: "about",
    };
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
