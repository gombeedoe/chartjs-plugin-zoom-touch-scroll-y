<template>
  <div id="app">
    <div>
      <ChartLine />
    </div>
    <div class="spacer">spacer</div>
  </div>
</template>

<script>
import ChartLine from "./components/ChartLine";

export default {
  name: "App",
  components: {
    ChartLine,
  },
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
.spacer {
  margin-top: 40px;
  height: 800px;
  background-color: lightgray;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
