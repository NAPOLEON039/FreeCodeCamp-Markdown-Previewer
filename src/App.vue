<template>
  <div id="app">
    <textarea v-model="inputText" name="text-editor" id="normal-text" cols="30" rows="10"></textarea>
    <div id="markdown-result">
      <markdown :content="inputText" />
    </div>
  </div>
</template>

<script>
import MarkdownItVue from 'markdown-it-vue'
import 'markdown-it-vue/dist/markdown-it-vue.css'

export default {
  name: 'app',
  data() {
    return {
      inputText: ''
    }
  },
  components: {
    Markdown: MarkdownItVue
  }
}
</script>

<style scoped>
#app {
  position: fixed;
  left: 0;
  top: 0;
  padding: 0;
  margin: 0; 
  height: 100%;
  width: 100%;
  display: flex;
  background-image: linear-gradient(120deg, #a6c0fe 0%, #f68084 100%);
}

#normal-text {
  height: 92vh;
  width: 50vw;
  margin: 20px;
  padding-top: 20px;
  font-size: 1.2em;
}

#markdown-result {
  display: inline-block;
  margin: 20px;
  padding: 20px;
  border: 0.1px solid rgb(187, 183, 183);
  height: 90vh;
  width: 50vw;
  background-color: white;
  white-space: pre-wrap;
  word-wrap: break-word;
  overflow-y: scroll;
}
</style>
