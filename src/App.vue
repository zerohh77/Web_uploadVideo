<template>
  <div id="app">
    <upload-video></upload-video>
  </div>
</template>

<script>
import UploadVideo from "@/components/UploadVideo/UploadVideo";

export default {
  name: 'App',
  components: {
    UploadVideo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
body{
  margin:0px;
}
</style>
