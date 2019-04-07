<template>
  <div id="app">
    <img id='vue-logo' alt="Vue logo" src="./assets/logo.png">

    <v-annotated-img src="https://picsum.photos/800/800"/>
  </div>
</template>

<script>
import AnnotatedImage from './components/AnnotatedImage.vue'

export default {
  name: 'app',
  components: {
      'v-annotated-img': AnnotatedImage
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  #vue-logo {
    width: 60px;
    height: 60px;
  }
</style>
