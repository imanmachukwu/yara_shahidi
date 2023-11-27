<template>
  <!--
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  -->
  <HomeView />
</template>

<script>
import { defineComponent } from 'vue'
//import HelloWorld from './components/HelloWorld.vue'
import HomeView from './components/Home.vue'
import Lenis from '@studio-freight/lenis'

const lenis = new Lenis({
  duration: 2,
})

console.log(lenis)

lenis.on('scroll', (e) => {
  console.log(e)
})

function raf(time) {
  lenis.raf(time)
  requestAnimationFrame(raf)
}

requestAnimationFrame(raf)

export default defineComponent({
  name: 'App',
  components: {
    HomeView,
  }
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Sorts+Mill+Goudy&display=swap');
@font-face {
  font-family: "Ogg Regular";
  src: url(../src/assets/font/Ogg-Regular-BF646c18fc3ed57.otf) format(OpenType);
}
@font-face {
  font-family: "Ranua";
  src: url(../src/assets/font/RanuaTrials-Light.otf) format(OpenType);
}
@font-face {
  font-family: "Ranua Regular";
  src: url(../src/assets/font/RanuaTrials-Regular.otf) format(OpenType);
}
@font-face {
  font-family: "Rebond Grotesque";
  src: url(../src/assets/font/Rebond\ Grotesque.otf) format(OpenType);
}

* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}

body {
  margin: 0px;
  background: #4F4386;
  overflow-x: hidden;
}
body::-webkit-scrollbar {
  display: none;
}

#app {
  font-family: "Rebond Grotesque", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

html.lenis {
  height: auto;
}

.lenis.lenis-smooth {
  scroll-behavior: auto;
}

.lenis.lenis-smooth [data-lenis-prevent] {
  overscroll-behavior: contain;
}

.lenis.lenis-stopped {
  overflow: hidden;
}

.lenis.lenis-scrolling iframe {
  pointer-events: none;
}
</style>
