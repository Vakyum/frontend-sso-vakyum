<script setup>
import { ref } from 'vue'

const companyName = import.meta.env.VITE_COMPANY_NAME || "Vakyum SSO"
const companyLogo = import.meta.env.VITE_COMPANY_LOGO || ref('/logo.png')
</script>

<template>
  <div class="flex items-center gap-3">
    <img
        :src="companyLogo"
        class="w-9 h-9 sm:w-12 sm:h-12 md:w-[60px] md:h-[60px] rounded-full object-cover"
    />
    <h1 class="text-xl sm:text-3xl md:text-4xl font-bold text-white">
      {{ companyName }}
    </h1>
  </div>
</template>

<style scoped>

</style>