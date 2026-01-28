<script setup>
import { ref, watch } from 'vue'


const dark = ref(false)


watch(dark, val => {
document.body.classList.toggle('dark', val)
})
</script>


<template>
<header>
<h1>Blog APP</h1>
<nav>
<RouterLink to="/">Home</RouterLink>
<RouterLink to="/about">About</RouterLink>
<RouterLink to="/Post-Detail">PostDetail</RouterLink>
<RouterLink to="/not-found">not-Found</RouterLink>
<button @click="dark = !dark">🌙</button>
</nav>
</header>
<RouterView />


<footer>© 2026 Blog Application - Emmza </footer>
</template>

