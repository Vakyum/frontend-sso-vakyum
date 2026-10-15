<script setup>
import companyIdentity from './components/companyIdentity.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col items-center justify-center gap-6 p-4">
    <companyIdentity />
    <div class="flex flex-col items-center justify-center gap-0.1 p-6 bg-zinc-900/60 border border-zinc-800/80 rounded-2xl backdrop-blur">
      <h1 class="text-xl sm:text-2xl font-bold text-white">Connexion</h1>
      <form action="/login" method="POST" class="flex flex-col items-center justify-center gap-6 p-6">
        <input
            type="email"
            name="email"
            id="email"
            placeholder="Email"
            required
            class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500 focus:outline-none focus:border-zinc-500" />
        <input
            type="password"
            name="password"
            id="password"
            placeholder="Mot de passe"
            required
            class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500 focus:outline-none focus:border-zinc-500" />
      </form>
    </div>
  </div>

</template>
