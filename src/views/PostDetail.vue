<script setup>
import { ref, onMounted } from 'vue'
import { useRoute, useRouter } from 'vue-router'

import axios from 'axios';

const options = {method: 'GET', url: 'https://api.oluwasetemi.dev/posts'};

try {
  const { data } = await axios.request(options);
  console.log(data);
} catch (error) {
  console.error(error);
}





const route = useRoute()
const router = useRouter()
const post = ref(null)


onMounted(async () => {
const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
post.value = await res.json()
})
</script>


<template>
<div class="container" v-if="post">
<button @click="router.back()">← Back</button>
<div class="card">
<h2>{{ post.title }}</h2>
<p>{{ post.body }}</p>
</div>
</div>
</template>


