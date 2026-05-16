<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  nome: '',
  cpf: '',
  telefone: '',
  rg: '',
  endereco: ''
})

const cadastrado = ref(false)

const handleCadastro = () => {
  console.log('Dados do Cadastro:', form)
  cadastrado.value = true
  
  // Reseta o formulário após 3 segundos (opcional)
  setTimeout(() => {
    cadastrado.value = false
    Object.keys(form).forEach(key => form[key] = '')
  }, 3000)
}
</script>

<template>
  <div class="max-w-2xl mx-auto py-12">
    <div class="glass-card p-8 animate-in fade-in slide-in-from-bottom-4 duration-500">
      <div class="flex items-center gap-4 mb-8">
        <div class="p-3 bg-vue-green/20 rounded-xl">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#42b883" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><line x1="19" x2="19" y1="8" y2="14"/><line x1="22" x2="16" y1="11" y2="11"/></svg>
        </div>
        <h2 class="text-3xl font-bold">Cadastro de Aluno</h2>
      </div>

      <form @submit.prevent="handleCadastro" class="space-y-6">
        <div class="space-y-2">
          <label class="text-sm font-semibold uppercase tracking-wider text-slate-400">Nome Completo</label>
          <input 
            v-model="form.nome" 
            type="text" 
            placeholder="Digite o nome..."
            class="w-full bg-black/40 border border-white/10 rounded-lg p-3 outline-none focus:border-vue-green/50 transition-colors"
            required
          >
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div class="space-y-2">
            <label class="text-sm font-semibold uppercase tracking-wider text-slate-400">CPF</label>
            <input 
              v-model="form.cpf" 
              type="text" 
              placeholder="000.000.000-00"
              class="w-full bg-black/40 border border-white/10 rounded-lg p-3 outline-none focus:border-vue-green/50 transition-colors"
              required
            >
          </div>
          <div class="space-y-2">
            <label class="text-sm font-semibold uppercase tracking-wider text-slate-400">Telefone</label>
            <input 
              v-model="form.telefone" 
              type="text" 
              placeholder="(00) 00000-0000"
              class="w-full bg-black/40 border border-white/10 rounded-lg p-3 outline-none focus:border-vue-green/50 transition-colors"
              required
            >
          </div>
        </div>

        <div class="space-y-2">
          <label class="text-sm font-semibold uppercase tracking-wider text-slate-400">RG</label>
          <input 
            v-model="form.rg" 
            type="text" 
            placeholder="Digite o RG..."
            class="w-full bg-black/40 border border-white/10 rounded-lg p-3 outline-none focus:border-vue-green/50 transition-colors"
            required
          >
        </div>

        <div class="space-y-2">
          <label class="text-sm font-semibold uppercase tracking-wider text-slate-400">Endereço</label>
          <input 
            v-model="form.endereco" 
            type="text" 
            placeholder="Rua, Número, Bairro..."
            class="w-full bg-black/40 border border-white/10 rounded-lg p-3 outline-none focus:border-vue-green/50 transition-colors"
            required
          >
        </div>

        <button 
          type="submit"
          class="w-full bg-vue-green text-slate-950 font-bold py-4 rounded-lg hover:bg-[#3fb27e] transition-all flex justify-center items-center gap-2 group"
        >
          <span v-if="!cadastrado">Cadastrar Aluno</span>
          <span v-else class="flex items-center gap-2 animate-bounce">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
            Sucesso!
          </span>
        </button>
      </form>

      <div v-if="cadastrado" class="mt-6 p-4 bg-vue-green/10 border border-vue-green/30 rounded-lg text-center animate-in fade-in zoom-in duration-300">
        <p class="text-vue-green font-medium">Os dados foram enviados para o console com sucesso!</p>
      </div>
    </div>

    <!-- Explanation Box for the Teacher -->
    <div class="mt-8 glass-card p-6 bg-yellow-400/5 border-yellow-500/20">
      <h4 class="text-yellow-400 font-bold mb-3 flex items-center gap-2 uppercase text-xs tracking-widest">
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="16" x2="12" y2="12"/><line x1="12" y1="8" x2="12.01" y2="8"/></svg>
        Explicação Técnica para a Apresentação
      </h4>
      <ul class="text-sm space-y-2 text-slate-400 pl-4 list-disc">
        <li><strong>SPA & Router:</strong> A navegação utiliza <code class="text-vue-green">RouterLink</code>, que intercepta cliques e renderiza componentes sem refresh.</li>
        <li><strong>Composition API:</strong> Utilizamos <code class="text-vue-green">reactive</code> para agrupar os dados do formulário e <code class="text-vue-green">ref</code> para o estado de sucesso.</li>
        <li><strong>Two-Way Binding:</strong> O <code class="text-vue-green">v-model</code> sincroniza automaticamente o que o usuário digita com nosso objeto JavaScript.</li>
        <li><strong>Event Handling:</strong> O formulário usa <code class="text-vue-green">@submit.prevent</code> para processar os dados sem recarregar a tela.</li>
      </ul>
    </div>
  </div>
</template>
