<script setup>
import companyIdentity from '../components/companyIdentity.vue'
import PasswordRegister from '../components/RegisterForm/PasswordRegister.vue'
import Birthdate from '../components/RegisterForm/BirthdateValidation.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col items-center justify-center gap-6 p-4">
    <companyIdentity />
    <div class="flex flex-col items-center justify-center gap-0.1 p-6 bg-zinc-900/60 border border-zinc-800/80 rounded-2xl backdrop-blur">
      <h1 class="text-xl sm:text-2xl font-bold text-white">Inscription</h1>
      <form action="/register" method="POST" class="flex flex-col items-center justify-center gap-6 p-6 w-full max-w-sm" id="register-form">
        <div class="flex w-80 flex-row gap-3">
          <input
              type="text"
              name="name"
              id="name"
              placeholder="Prénom"
              required
              class="flex-1 w-1/2 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500 focus:outline-none focus:border-zinc-500" />
          <input
              type="text"
              name="surname"
              id="surname"
              placeholder="Nom"
              required
              class="flex-1 w-1/2 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500 focus:outline-none focus:border-zinc-500" />
        </div>
        <Birthdate />
        <input
            type="email"
            name="email"
            id="email"
            placeholder="Email"
            required
            class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500
              focus:outline-none focus:border-zinc-500" />
        <PasswordRegister />
        <div class="flex flex-row items-left gap-1.5 w-80 text-xs">
          <input
              type="checkbox"
              name="terms-check"
              id="terms-check"
              required
              class="accent-cyan-700" />
          <label for="remember">J'accepte les <a href="https://vakyum.fr/cgu"
              class="text-cyan-700 duration-500 hover:brightness-125 active:brightness-150">Conditions générales d'utilisation</a>. </label>
        </div>
        <button
            type="submit"
            form="login-form"
            value="Submit"
            class="w-80 h-10 bg-cyan-700 text-white rounded-xl border border-zinc-700 font-semibold duration-500
              hover:brightness-85 hover:duration-500
              active:brightness-65">
          <i class="bi bi-person-plus-fill"></i> S'inscrire
        </button>
      </form>
    </div>
    <p class="text-zinc-400">
      Vous possedez déjà un compte ?
      <RouterLink to="/" class="text-cyan-700 duration-500 hover:brightness-125 active:brightness-150">
        Se connecter
      </RouterLink>
    </p>
  </div>
</template>

<style scoped>

</style>