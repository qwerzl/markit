<template>
  <!--<div data-tauri-drag-region class="titlebar">
    <div class="windowTitle">Untitled</div>
    <div class="wordCount">{{ wordCount }} Characters</div>
  </div>-->
  <div id="vditor" />
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Vditor from 'vditor';
//import 'vditor/dist/index.css';

const vditor = ref(Vditor);
var wordCount = ref(0);
onMounted(() => {
  vditor.value = new Vditor('vditor', {
    "typewriterMode": true,
    "counter": {
      "enable": true,
      after(count) {
        wordCount.value = count;
      }
    },
    "preview": {
      "math": {
        "engine": "MathJax",
        "macros": {
          "bf": "{\\boldsymbol f}",
          "bu": "{\\boldsymbol u}",
          "bv": "{\\boldsymbol v}",
          "bw": "{\\boldsymbol w}"
        }
      }
    }
  });
});
</script>

<style></style>
