<template>
  <div class="max-w-4xl mx-auto py-12">
    <div class="glass-card p-10 text-center space-y-8 animate-in fade-in slide-in-from-bottom-4 duration-700">
      <div class="flex justify-center">
        <div class="p-5 bg-vue-green/10 rounded-full border border-vue-green/20">
          <svg width="60" height="60" viewBox="0 0 256 221">
            <path fill="#41B883" d="M204.8 0H256L128 220.8 0 0h97.92L128 51.2 157.44 0h47.36z"/>
            <path fill="#35495E" d="M157.44 0L128 51.2 98.56 0H51.2L128 132.48 204.8 0h-47.36z"/>
          </svg>
        </div>
      </div>
      
      <div class="space-y-4">
        <h2 class="text-4xl font-bold tracking-tight">Bem-vindo ao Sistema Acadêmico</h2>
        <p class="text-xl text-slate-400 max-w-2xl mx-auto leading-relaxed">
          Esta é a página inicial da sua aplicação SPA desenvolvida com <span class="text-vue-green">Vue.js</span>. 
          Utilize o menu superior para navegar entre as seções.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 pt-8">
        <div class="p-6 rounded-xl bg-white/5 border border-white/10 text-left space-y-2">
          <h4 class="font-bold text-vue-green uppercase text-xs tracking-widest">SPA</h4>
          <p class="text-sm opacity-70 italic">Navegação instantânea sem recarregar a página.</p>
        </div>
        <div class="p-6 rounded-xl bg-white/5 border border-white/10 text-left space-y-2">
          <h4 class="font-bold text-vue-green uppercase text-xs tracking-widest">Componentes</h4>
          <p class="text-sm opacity-70 italic">Estrutura modular e organizada.</p>
        </div>
        <div class="p-6 rounded-xl bg-white/5 border border-white/10 text-left space-y-2">
          <h4 class="font-bold text-vue-green uppercase text-xs tracking-widest">Formulários</h4>
          <p class="text-sm opacity-70 italic">Coleta de dados com Composition API.</p>
        </div>
      </div>

      <div class="pt-10">
        <router-link to="/cadastro" class="inline-flex items-center gap-2 px-8 py-4 bg-vue-green text-slate-950 font-bold rounded-lg hover:scale-105 transition-transform active:scale-95 shadow-lg shadow-vue-green/20">
          Acessar Cadastro
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>
        </router-link>
      </div>
    </div>
  </div>
</template>
