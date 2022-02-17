<template>
  <div id="app">
    <textarea v-model="inputText" name="text-editor" id="editor" cols="30" rows="10"></textarea>
    <div id="preview">
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
      inputText: 'Some basic Markdown tips:\n# Heading \n\n## Sub-heading\n\n[Here\'s a link to visit FreeCodeCamp](https://www.freecodecamp.org)\n\n`Inline code`\n\nA code block:\n```javascript\nlet projectName = "Markdown Previewer";\n\nconsole.log(`I am working on ${projectName} project`);\n// I am working on Markdown Previewer project\n```\n\n* List item 1\n* List item 2\n\n> This is a blockquote\n\n**This is how you write bold text.**\n\nHere\'s an image:\n![Place to write alt text](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse1.mm.bing.net%2Fth%3Fid%3DOIP.kwkc_7Yosj69YWbWlDQ-oAHaEo%26pid%3DApi&f=1)'
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

#editor {
  height: 92vh;
  width: 50vw;
  margin: 20px;
  padding-top: 20px;
  padding-left: 15px;
  font-size: 1.2em;
  resize: none;
}

#preview {
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
