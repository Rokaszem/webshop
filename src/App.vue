<template>
  <NavigationBar />
  <!--<img alt="Vue logo" src="./assets/logo.png" />-->
  <!--<HelloWorld msg="Welcome to Your Vue.js App" />-->
  <Products />
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";
import NavigationBar from "./components/NavigationBar.vue";
import Products from './components/Products.vue';

export default {
  name: "App",
  components: {
    //HelloWorld,
    NavigationBar,
    Products
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body {
  margin: 0;
}
</style>
