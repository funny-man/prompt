<template>
  <div id="app">
    <prompt ref="prompt"></prompt>
    <button @click="showPrompt">点我</button>
  </div>
</template>

<script>
import Prompt from './components/prompt.vue'

export default {
  name: 'app',
  components: {
    'prompt': Prompt
  },
  methods: {
    showPrompt() {
      this.$refs.prompt.show();
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
