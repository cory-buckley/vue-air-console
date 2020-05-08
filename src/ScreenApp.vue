<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div>Screen</div>
    <div>{{ messages }}</div>
  </div>
</template>

<script>

export default {
  name: 'ScreenApp',
  data() {
    return {
      messages: ''
    }
  },
  mounted() {
    this.$airconsole.onMessage = (from, data) => {
      // We receive a message -> Send message back to the device
      this.$airconsole.message(from, "Full of pixels!");
      this.messages = data
    };
  }
}
</script>

<style>
body {
  background: #3b3b3b;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}
</style>
