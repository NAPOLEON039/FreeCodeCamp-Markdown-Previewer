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
      inputText: 'Some basic Markdown tips:\n# Heading \n\n## Sub-heading\n\n[Here\'s a link to visit FreeCodeCamp](https://www.freecodecamp.org)\n\n`Inline code`\n\nA code block:\n```javascript\nlet projectName = "Markdown Previewer";\n\nconsole.log(`I am working on ${projectName} project`);\n// I am working on Markdown Previewer project\n```\n\n* List item 1\n* List item 2\n\n> This is a blockquote\n\n**This is how you write bold text.**\n\nHere\'s an image:\n![Place to write alt text](https://uc6e1721bf791dc1cf3698fd630a.previews.dropboxusercontent.com/p/thumb/AAvssN2W-BzbQEPNglQIE4R555ZeVimwYXhLpDYm1i-eHpNGGRSvkgwLQ6j2SWdyBYA26IrOzHK9-mLyHr3HWx8sCxEAumGwnA42518_RbIOM95MnktvDgNsrevj7BaZj6ZH8Hj2luqJeSLc5wPsalvI5MgFfM3vpkoHKrqfU9VzSMlyInOxLFQTQ61JHisoyPszJnfWDXgcARgtQMsn2bhFpPA8z3dRM1DTx3Me7iysHD2Kt8yDcAdpUXxXEOW7_5vWCTSZTjAiQtdI1WsPe-NoLrKU6j4Thgy9CQI221KBDnTx-Yr1GJWGsf0eiSxtTfQb4Hoh57OIo2uiwoN3Wq4cYJsK9tLvpo6RnzHtPlwI8vF0YqkUNN-5Wfj2EPjxzOw/p.jpeg?fv_content=true&size_mode=5)'
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
