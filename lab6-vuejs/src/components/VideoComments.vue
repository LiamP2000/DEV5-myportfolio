<script setup>

import { ref, reactive } from 'vue';


 let title = ref("");
 let comments = reactive([]);

 const addComment = () => {
   comments.push(title.value);
   console.log("werkt et?");
 };

</script>

<template>
  <div>
    <h1>Reactions</h1>

    <ul>
      <li v-for="comment in comments" :key="comment">
        {{ comment }}
      </li>
    </ul>

    <input type="text" v-model="title">
    <button @click="addComment">Add comment</button>
  </div>
</template>

<style scoped>

</style>
