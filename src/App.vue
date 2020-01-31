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

export default {
  name: 'app',
  data() {
    return {
      inputText: ''
    }
  },
  components: {
    Markdown: MarkdownItVue
  },
  methods: {
    convertToMarkdown() {
      document.querySelector('#markdown-result').innerHTML = marked(this.inputText)
    }
  }
}
</script>

<style>
#markdown-result {
  display: inline-block;
  margin: 0 10px;
  border: 0.5px solid rgb(99, 97, 97);
  height: 150px;
  width: 300px;
}
</style>
