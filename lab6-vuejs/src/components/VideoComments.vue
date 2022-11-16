<script setup>

import { ref, reactive, onMounted } from 'vue';

  let comments = reactive({ comments : [] });
  let text = ref("");

  onMounted(() => {
    // fetch API
    fetch("https://lab5-p379.onrender.com/api/v1/messages/")
      .then((response) => response.json())
      .then((data) => {
        comments.comments = data;
        console.log(data);
      });
  });

  




</script>

<template>
  <div>
  </div>
</template>

<style scoped>

</style>
