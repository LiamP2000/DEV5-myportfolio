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

  const addComment = () => {
    let data = {
      user: "Liam",
      text: text.value
    };
    fetch("https://lab5-p379.onrender.com/api/v1/messages/", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(comment),
    })
      .then((response) => response.json())
      .then((data) => {
        console.log(data);
        comments.comments.push({
          _id: data.data._id,
          user: data.data.user,
          text: data.data.text,
        });
      });
  };

  




</script>

<template>
  <div>
  </div>
</template>

<style scoped>

</style>
