<script setup lang="ts">
import editor from '@coffic/juice-editor'

const html = `
  <h1 class='ml-0'>Juice Editor</h1>
  <p class='ml-0'>Hello World</p>
  <h2>Link</h2>
  You can find the source code of this playground on ➡️ <a href='https://github.com/CofficLab/JuiceEditor-Playground'>GitHub</a>
`

editor.onCreate = () => {
  console.log('editor created')

  editor.setDrawLink('/drawio/webapp/index.html?')
  editor.setHtml(html)
}
</script>

<template>
  <div style="width: 100%; height: 100%;">
    <juice-editor />
  </div>
</template>
