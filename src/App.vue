<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <ciclo-de-vida></ciclo-de-vida>
  <ping-when-mounted></ping-when-mounted>
</template>

<script>
import CicloDeVida from "./components/CicloDeVida.vue";
import PingWhenMounted from "./components/PingWhenMounted.vue";

export default {
  name: "App",
  components: {
    CicloDeVida,
    PingWhenMounted,
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
