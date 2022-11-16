<script setup>
  // import VideoPlayer.vue
  import VideoPlayer from './components/VideoPlayer.vue'
  // import VideoDetails.vue
  import VideoDetails from './components/VideoDetails.vue'
  // import VideoComments.vue
  import VideoComments from './components/VideoComments.vue'

</script>

<template>
  <div class="app">
    <VideoPlayer />
    <VideoDetails />
    <VideoComments />

  </div>
</template>

<style scoped>
  .app {
    display: grid;
    grid-template-columns: 8fr 4fr;
    grid-template-rows: 4fr 8fr;
    grid-template-areas:
      "video video"
      "details comments";

  }

</style>
