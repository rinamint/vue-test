<template>
  <div id="app">
    <header class="header">
      <a href="#" class="logo">
        <img alt="Vue logo" src="./assets/logo.png" />
      </a>
    </header>
    <Main />
    <Aside />
    <footer class="footer">
      <p>Подвал с контактной информацией</p>
    </footer>
  </div>
</template>

<script>
import Main from "./components/Main.vue";
import Aside from "./components/Aside.vue";

export default {
  name: "App",
  components: {
    Main,
    Aside,
  },
};
</script>

<style>
#app {
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-top: 10px;
}

.header {
  display: flex;
  margin-top: 10px;
  padding: 10px 20px;
  background: #d3d3d3;
}
.logo {
  width: 50px;
}
.logo > img {
  max-width: 100%;
  height: auto;
  margin: auto;
}
.footer {
  margin-top: 10px;
  padding: 10px 20px;
  background: #d3d3d3;
}
</style>
