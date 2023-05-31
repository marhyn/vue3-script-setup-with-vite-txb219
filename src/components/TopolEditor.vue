<script setup>
import { TopolEditor, TopolPlugin } from '@topol.io/editor-vue'

const topolOptions = {
  id: '#app',
  authorize: {
    apiKey: 'd4U1ZDySMKUfF8wKPcyN2pwo9WFxvAFNWiBp51x09so8RHFc7mnynzYU344H',
    userId: 'userId'
  }
}

const onInit = () => {
  fetch('https://tlapi.github.io/topol-editor/templates/1.json')
    .then((response) => response.text())
    .then((template) => {
      //Load the template in Editor
      TopolPlugin.load(template);
    });}
</script>

<template>
  <TopolEditor :options="topolOptions" @on-init="onInit" />
</template>
