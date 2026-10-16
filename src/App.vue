<script setup>
import companyIdentity from './components/companyIdentity.vue'
import rememberCheck from './components/rememberCheck.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col items-center justify-center gap-6 p-4">
    <companyIdentity />
    <div class="flex flex-col items-center justify-center gap-0.1 p-6 bg-zinc-900/60 border border-zinc-800/80 rounded-2xl backdrop-blur">
      <h1 class="text-xl sm:text-2xl font-bold text-white">Connexion</h1>
      <form action="/login" method="POST" class="flex flex-col items-center justify-center gap-6 p-6" id="login-form">
        <input
            type="email"
            name="email"
            id="email"
            placeholder="Email"
            required
            class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500
              focus:outline-none focus:border-zinc-500" />
        <input
            type="password"
            name="password"
            id="password"
            placeholder="Mot de passe"
            required
            class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500
              focus:outline-none focus:border-zinc-500" />
        <div class="flex flex-row text-xs leading-none justify-between gap-15">
          <rememberCheck />
          <span class="hover:text-white active:text-cyan-700">Mot de passe oublié ?</span>
        </div>
        <button
            type="submit"
            form="login-form"
            value="Submit"
            class="w-80 h-10 bg-cyan-700 text-white rounded-xl border border-zinc-700 font-semibold duration-500
              hover:brightness-85 hover:duration-500
              active:brightness-65">
          <i class="bi bi-person-check-fill"></i> Se connecter
        </button>
      </form>
    </div>
    <div>
      <p>Pas encore de compte ? <a class="text-cyan-700 duration-500
        hover:brightness-125 duration-500
        active:brightness-150 duration-500">S'inscrire</a></p>
    </div>
  </div>

</template>
