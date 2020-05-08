<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div>Controller</div>
    <button @click="sendMessage">Send Message</button>
    <div>{{ messages }}</div>
  </div>
</template>

<script>

export default {
  name: 'ControllerApp',
  data() {
    return {
      messages: ''
    }
  },
  methods: {
    sendMessage() {
      console.log(this.$airconsole.getControllerDeviceIds());
      this.$airconsole.message(this.$screen, "How are you?")
    }
  },
  mounted() {
    this.$airconsole.onMessage = (from, data) => {
      this.messages = data
    }
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
