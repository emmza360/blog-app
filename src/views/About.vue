<script setup>
import { ref, watch } from 'vue'


const dark = ref(false)


watch(dark, val => {
document.body.classList.toggle('dark', val)
})
</script>

<template>
<div class="container">
      <div class="card">
        <h2>About Me</h2>
        <p><strong>Name:</strong> Emmza Laleye</p>
        <p><strong>Profession:</strong> Software Engineer</p>
        <p><strong>Experience:</strong> Former Intern at FNB</p>
        <p>
          This blog application was built using Vue 3 and Vue Router,
          demonstrating API consumption, routing, dark mode, animations,
          and modern UI practices.
        </p>
      </div>
    </div>
</template>