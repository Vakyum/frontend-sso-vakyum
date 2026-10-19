<script setup>
import { inject } from 'vue';

const email = inject('userEmail')
</script>

<template>
  <div class="flex flex-col items-center justify-center gap-0.1 p-6 bg-zinc-900/60 border border-zinc-800/80 rounded-2xl backdrop-blur">
    <form class="flex flex-col items-center justify-center gap-6 p-6" id="access-password-reset">
      <label for="check-code" class="text-xs">Code de vérification envoyé à
        <span class="text-white font-semibold"> {{ email }}</span>.</label>
      <input
        type="number"
        name="check-code"
        id="check-code"
        placeholder="Code de vérification"
        required
        class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 text-white border border-zinc-700 placeholder-zinc-500
          focus:outline-none focus:border-zinc-500" />
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

</template>

<style scoped>

</style>