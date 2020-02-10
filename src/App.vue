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
  justify-content: center;
  align-items: center;
}

#normal-text {
  height: 150px;
  width: 300px;
}

#markdown-result {
  display: inline-block;
  margin: 0 10px;
  border: 0.5px solid rgb(99, 97, 97);
  height: 150px;
  width: 300px;
  background-color: white;
  white-space: pre-wrap;
  word-wrap:break-word;
  overflow-y: scroll;
}
</style>
