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
    <!-- Header -->

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
  height: 85vh;
  overflow: hidden;
  background-image: url('/img/landscape.webp');
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
  font-family: 'Georgia', serif;
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

/* Header en bas pour mobile */
.header {
  position: fixed;
  bottom: 0;
  width: 100%;
}

/* Styles pour les écrans plus grands */
@media (min-width: 768px) {
  .hero-section {
    padding: 30px;
    max-width: 700px; /* Limite la largeur de la section pour une lecture facile */
  }

  .welcome-text {
    font-size: 2.5em; /* Agrandit le titre pour remplir l’espace */
  }

  .dedication-text {
    font-size: 1.5em; /* Texte de dédicace plus grand */
  }

  .intro-text {
    font-size: 1.2em;
    max-width: 85%;
  }
}

/* Header en haut pour desktop */
@media (min-width: 1024px) {
  .header {
    position: fixed;
    top: 0;
    width: 100%;
  }

  .hero-section {
    padding: 40px;
    max-width: 900px;
  }

  .welcome-text {
    font-size: 3em;
  }

  .dedication-text {
    font-size: 1.8em;
  }

  .intro-text {
    font-size: 1.3em;
    max-width: 70%;
  }

  .overlay {
    background-color: rgba(0, 0, 0, 0.3); /* Légèrement plus clair sur grand écran */
  }
}
</style>
