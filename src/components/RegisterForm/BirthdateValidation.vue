<script setup>
import { ref, computed } from 'vue'

const birthdate = ref('')

// Propriété calculée : se met à jour automatiquement quand birthdate change
const age = computed(() => {
  if (!birthdate.value) return null

  // 1. Convertir la chaîne "YYYY-MM-DD" en objet Date
  const birthDateObj = new Date(birthdate.value)

  // 2. Calculer la différence
  const diff = Date.now() - birthDateObj.getTime()
  const ageDate = new Date(diff)

  return Math.abs(ageDate.getUTCFullYear() - 1970)
})

const inputClasses = computed(() => {
  if (!birthdate.value) {
    return 'border-zinc-700 focus:border-zinc-500' // État par défaut
  }

  return age.value >= 15
      ? 'border-emerald-500 text-emerald-400 focus:border-emerald-500' // Valid (≥ 15y)
      : 'border-rose-500 text-rose-400 focus:border-rose-500'           // Invalid (< 15y)
})
</script>

<template>
  <div class="flex flex-col gap-2">
    <label for="birthdate" class="text-xs">Date de naissance</label>
    <input
        type="date"
        name="birthdate"
        id="birthdate"
        v-model="birthdate"
        placeholder="Date de naissance"
        required
        :class="inputClasses"
        class="w-80 h-12 px-4 rounded-xl bg-zinc-800/80 border transition-colors outline-none"
    />

    <p v-if="age !== null && age < 15" class="text-xs text-rose-400 duration-500">
      <i class="bi bi-x-circle"></i> Il faut avoir 15ans minimum pour s'inscrire !
    </p>
  </div>
</template>