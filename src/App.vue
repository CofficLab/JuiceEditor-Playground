<script setup lang="ts">
import { defineJuiceEditor, EventName, EventType } from '@coffic/juice-editor'

defineJuiceEditor()

window.addEventListener(EventName, ((event: CustomEvent) => {
  console.log(EventName, event)

  if (event.detail.type === EventType.editorReady) {
    let drawLink = "/drawio/webapp/index.html?"
    console.log('editorReady, set draw link', drawLink);
    (window as any).api.config.setDrawIoLink(drawLink);
    (window as any).api.node.setHTML("<h1 class='ml-0'>Juice Editor</h1><p class='ml-0'>Hello World</p>");
  }
}) as EventListener)
</script>

<template>
  <div style="width: 100%; height: 100%;">
    <juice-editor />
  </div>
</template>
