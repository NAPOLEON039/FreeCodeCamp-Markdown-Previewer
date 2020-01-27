<template>
  <div id="app">
    <textarea v-model="inputText" name="text-editor" id="normal-text" cols="30" rows="10"></textarea>
    <textarea v-model="markdownResult"></textarea>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data() {
    return {
      inputText: '',
      markdownResult: ''
    }
  }
}
</script>

<style>
#app {
}
</style>
