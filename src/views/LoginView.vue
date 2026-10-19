<script setup>
import {computed, provide, ref} from 'vue'

import companyIdentity from '../components/companyIdentity.vue'
import rememberCheck from '../components/LoginForm/rememberCheck.vue'
import AccessPasswordReset from "../components/LoginForm/AccessPasswordReset.vue";

const email = ref('')
const step = ref('login')

const updateEmail = (newEmail) => {
  // For send email in case of Password reset -> AccessPasswordReset component.
  email.value = newEmail
}

provide('userEmail', email)

const showPasswordReset = ref(false)

const togglePasswordReset = () => {
  // To show AccessPasswordReset on click on "Forgot password".
  showPasswordReset.value = !showPasswordReset.value
}
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
            v-model="email"
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
          <span @click="togglePasswordReset()" class="hover:text-white active:text-cyan-700 cursor-pointer">Mot de passe oublié ?</span>
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
      <p class="text-zinc-400">
        Pas encore de compte ?
        <RouterLink to="/register" class="text-cyan-700 duration-500 hover:brightness-125 active:brightness-150">
          S'inscrire
        </RouterLink>
      </p>
    </div>
    <Transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="transform scale-95 opacity-0 -translate-y-2"
        enter-to-class="transform scale-100 opacity-100 translate-y-0"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="transform scale-100 opacity-100 translate-y-0"
        leave-to-class="transform scale-95 opacity-0 -translate-y-2"
    >
      <div v-if="showPasswordReset">
        <AccessPasswordReset />
      </div>
    </Transition>
  </div>
</template>