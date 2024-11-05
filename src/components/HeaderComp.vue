<template>
  <header class="header">
    <div class="logo-container">
      <img src="/favicon.png" alt="Logo Memorial" class="logo" />
    </div>
    <RadialNavComp class="radial-nav" />
  </header>
</template>

<script setup>
import { defineProps } from 'vue';
import RadialNavComp from "@/components/RadialNavComp.vue";

defineProps({
  initials: {
    type: String,
    default: "Memorial Vitor Costa", // Remplace par les initiales souhaitées
  },
});
</script>

<style scoped>
.header {
  position: fixed;
  bottom: 0; /* Positionne le header en bas de l’écran */
  width: 100%;
  height: 15vh;
  padding: 15px 3rem;
  background: #E1E1E1;
  display: flex;
  align-items: center;
  justify-content: space-between; /* Place RadialNav à droite */
  box-shadow: 0 -2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  width: 40px;
  height: auto;
  margin-right: 10px;
}

.radial-nav {
  position: relative;
}

@media (min-width: 769px) and (max-width: 1024px) {
  .header {
    height: 12vh; /* Ajuste la hauteur pour les tablettes */
    padding: 15px 3rem; /* Ajuste le padding */
  }

  .logo {
    width: 35px; /* Ajuste la taille du logo pour tablette */
  }
}

@media (min-width: 1025px) {
  /* Styles pour les grands écrans (desktop) */
  .header {
    top: 0; /* Positionne le header en bas de l’écran */
  }

  .logo {
    width: 40px; /* Taille standard pour desktop */
  }
}
</style>
