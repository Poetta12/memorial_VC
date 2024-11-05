<template>
  <div class="home">
    <div class="overlay"></div>
    <div class="hero-section">
      <h1 class="welcome-text">Mémorial Vitor Costa</h1>
      <p class="dedication-text">"À jamais dans nos cœurs"</p>
      <p class="intro-text">
        Ce mémorial est un hommage à une vie pleine de souvenirs, de joie et de sagesse.
      </p>
    </div>

    <!-- Header en bas de page -->
    <HeaderComp :initials="'Vitor Costa'" />
  </div>
</template>

<script setup>
import HeaderComp from "@/components/HeaderComp.vue";
</script>

<style scoped>
/* Style mobile-first */
.home {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  overflow: hidden;
  background-image: url('@/assets/landscape.jpg'); /* Image symbolique en fond */
  background-size: cover;
  background-position: center;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4); /* Filtre sombre pour renforcer la lisibilité */
  z-index: 1;
}

.hero-section {
  position: relative;
  z-index: 2; /* Au-dessus de l'overlay */
  text-align: center;
  color: white;
  padding: 20px;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.6);
}

.welcome-text {
  font-size: 2em;
  font-weight: bold;
  margin: 0;
  font-family: 'Georgia', serif; /* Police élégante pour un effet mémorial */
}

.dedication-text {
  font-size: 1.2em;
  margin: 10px 0;
  font-style: italic;
}

.intro-text {
  font-size: 1em;
  max-width: 80%;
  margin: 20px auto 0;
  line-height: 1.6;
}

/* Header en bas */
.header {
  position: fixed;
  bottom: 0;
  width: 100%;
}
</style>
