<template>
  <v-app>
    <v-main>
      <Suspense>
        <GroupeSecuriteChoix 
          modeChoix="unique"
          @choixGroupeSecurite="receptionGroupeSecurite"
        />
      </Suspense>
    </v-main>
  </v-app>
</template>

<script setup>
import GroupeSecuriteChoix from './components/GroupeSecuriteChoix.vue';

const receptionGroupeSecurite = (jsonData) => {
  console.log(`Réception groupe sécurité \njson: ${jsonData}`)
  if (window.opener && typeof window.opener.receptionGroupeSecurite24 === 'function') {
    window.opener.receptionGroupeSecurite24(jsonData)
  }
}
</script>
