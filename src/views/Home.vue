<script setup>
import { ref, onMounted } from 'vue'


const posts = ref([])
const loading = ref(true)
const error = ref(null)


onMounted(async () => {
try {
const res = await fetch('https://jsonplaceholder.typicode.com/posts?_limit=9')
if (!res.ok) throw new Error('API Error')
posts.value = await res.json()
} catch (err) {
error.value = err.message
} finally {
loading.value = false
}
})
</script>


<template>
<div class="container">
<h2>Latest Blog Posts</h2>
<p v-if="loading">Loading posts...</p>
<p v-if="error" class="error">{{ error }}</p>


<div class="grid">
<div class="card" v-for="post in posts" :key="post.id">
<h3>{{ post.title }}</h3>
<p>{{ post.body.substring(0, 90) }}...</p>
<RouterLink :to="`/post/${post.id}`">Read more →</RouterLink>
</div>
</div>
</div>
</template>
