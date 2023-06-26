<template>
  <div>
    <!-- <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a> -->
    <!-- <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a> -->
    <input type="textarea" v-model="input_content" placeholder="请输入需要转换的文字">
    <!-- <audio controls ref="audio" class="aud"  >
      <source :src="mp3URL" /> hidden
      <source src="../test.mp3" />
    </audio> -->
    <button @click="startChange()">开始语音转换</button>
    <!-- <button @click="startplay()">开始播放</button> -->
  </div>
  <!-- <HelloWorld msg="Vite + Vue" /> -->
</template>
<script setup lang="ts">
import { ref } from "vue";
// import mp3 from  '../test.mp3'
// import tts from '../synth.js'
import tts from '../synth'
// let audio = null;
// const mp3URL = ref('')
const input_content = ref('')
// function startplay() {
//    audio = new Audio();
//    audio.src = mp3;
//   //  audio.loop = "loop";
//    audio.play();
   
//  }
 function startChange(){
  tts.speek(input_content.value)
 }
</script>
<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
