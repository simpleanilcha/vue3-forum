<template>
  <div>
    <h1>Home Page</h1>
    <div v-for="thread in threads" :key="thread.id">
      <h2>{{ thread.title }}</h2>
      <div v-for="postId in thread.posts" :key="postId">
        <p>{{ userById(postById(postId).userId).name }}</p>
        <p>{{ postById(postId).text }}</p>
      </div>
    </div>
    <pre>
      {{ threads }}
    </pre>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import sourceData from '@/data.json'
// console.log('sourceData', sourceData)
const dataSource = ref(sourceData)
// console.log('dataSource', dataSource)

const threads = ref(sourceData.threads)
const posts = ref(sourceData.posts)
const users = ref(sourceData.users)

function postById (postId) {
  // console.log('posts', posts)
  return posts.value.find(p => p.id === postId)
}
function userById (userId) {
  // console.log('users', users)
  return users.value.find(u => u.id === userId)
}
</script>

<style scoped>

</style>