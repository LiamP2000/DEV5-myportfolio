<script setup>

import { ref, reactive, onMounted } from 'vue';


 let title = ref("");
 //let comments = reactive([]);
 let comment = ref('');

 const addComment = () => {
   comments.push(title.value);
   console.log("werkt et?");
 };

 //fetch reactions 
 onMounted(() => {
  // fetch API
  let api_url = "https://lab5-p379.onrender.com/api/v1/messages/"
    fetch(api_url)
        .then((response) => response.json())
        .then((data) => {
            console.log(data);
        });
            
        })

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
