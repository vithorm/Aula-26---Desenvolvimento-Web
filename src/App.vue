<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="h-20 border-b border-white/5 flex items-center px-8 bg-slate-950/80 sticky top-0 z-50 backdrop-blur-sm">
    <div class="flex items-center gap-3">
      <svg width="40" height="35" viewBox="0 0 256 221" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid">
        <path fill="#41B883" d="M204.8 0H256L128 220.8 0 0h97.92L128 51.2 157.44 0h47.36z"/>
        <path fill="#41B883" d="M0 0l128 220.8L256 0h-51.2L128 132.48 51.2 0H0z"/>
        <path fill="#35495E" d="M157.44 0L128 51.2 98.56 0H51.2L128 132.48 204.8 0h-47.36z"/>
      </svg>
      <div>
        <h1 class="text-xl font-bold m-0 leading-tight">Aula 25 - <span class="vue-accent">Vue.js</span></h1>
        <p class="text-[0.75rem] opacity-60 m-0 uppercase tracking-wider">Desenvolvimento Web II</p>
      </div>
    </div>
    <nav class="ml-auto flex gap-6">
      <RouterLink to="/" class="text-sm font-medium hover:text-vue-green transition-colors">Home</RouterLink>
      <RouterLink to="/cadastro" class="text-sm font-medium hover:text-vue-green transition-colors">Cadastro</RouterLink>
    </nav>
  </header>

  <main class="max-w-6xl mx-auto p-6 min-h-[calc(100vh-5rem)]">
    <RouterView />
  </main>
</template>

<style scoped>
nav a.router-link-exact-active {
  color: #42b883;
}
</style>
