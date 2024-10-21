<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import { defineJuiceEditor, EventName, EventType } from '@coffic/juice-editor'

defineJuiceEditor()

window.addEventListener(EventName, (event) => {
  console.log(EventName, event)

  if (event.detail.type === EventType.editorReady) {
    let drawLink = "/drawio/webapp/index.html?"
    console.log('editorReady, set draw link', drawLink)
    window.api.config.setDrawIoLink(drawLink)
    window.api.node.setHTML("<h1>Juice Editor</h1><p>Hello World</p>")
  }
})
</script>

<template>
  <div style="width: 100%; height: 100%;">
    <juice-editor />
  </div>
</template>