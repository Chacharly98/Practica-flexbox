<template>
  <div id="app">
    <h1>Proyecto charly</h1>
    <input v-model="name" />
    <br />
    <br />
    <label>{{ toLower }}</label>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: ""
    };
  },
  computed: {
    toLower() {
      return this.name.toLowerCase();
    }
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