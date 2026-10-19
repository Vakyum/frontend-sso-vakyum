<script setup>
import companyIdentity from '../components/companyIdentity.vue'
import PasswordRegister from "../components/RegisterForm/PasswordRegister.vue";
</script>

<template>
  <div class="min-h-screen flex flex-col items-center justify-center gap-6 p-4">
    <companyIdentity />
    <div class="flex flex-col items-center justify-center gap-0.1 p-6 bg-zinc-900/60 border border-zinc-800/80 rounded-2xl backdrop-blur">
      <h1 class="text-xl sm:text-2xl font-bold text-white">Nouveau mot de passe</h1>
      <form action="/login" method="POST" class="flex flex-col items-center justify-center gap-6 p-6" id="login-form">
        <PasswordRegister />
        <button
            type="submit"
            form="access-password-reset"
            value="Submit"
            class="w-80 h-10 bg-green-800 text-white rounded-xl border border-zinc-700 font-semibold duration-500
          hover:brightness-85 hover:duration-500
          active:brightness-65">
          <i class="bi bi-person-fill-lock"></i> Réinitialiser le mot de passe
        </button>
      </form>
    </div>
  </div>
</template>