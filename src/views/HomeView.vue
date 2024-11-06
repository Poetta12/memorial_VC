<template>
  <div class="home">
    <div class="overlay"></div>
    <div class="hero-section">
      <h1 class="welcome-text">Mémorial Vitor Costa</h1>
      <!-- Cadre pour la photo -->
      <div class="photo-frame">
        <div class="blur-frame"></div>
        <img src="/pere/pere_1_noBG.png" alt="Photo de Vitor Costa" class="photo" />
      </div>
      <p class="dedication-text">"À jamais dans nos cœurs"</p>
      <p class="intro-text">
        Ce mémorial est un hommage à une vie pleine de souvenirs, de joie et de sagesse.
      </p>
    </div>
    <!-- Header -->
  </div>
</template>

<script setup>
const medals = ["GALERIA", "MEMORIAS", "LIVRO DE VISITAS", "CONTACTO"];
import HeaderComp from "@/components/HeaderComp.vue";
</script>

<style scoped>
/* Style mobile-first */
.pages-btn {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: linear-gradient(135deg, #f0e68c, #d8c746); /* Dégradé de couleurs */
  color: #333;
  font-weight: bold; /* Mettre le texte en gras */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Ombre pour profondeur */
  transition: transform 0.3s, box-shadow 0.3s; /* Transition pour effet hover */
}

.pages-btn:hover {
  transform: scale(1.05); /* Légère augmentation au survol */
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3); /* Ombre plus prononcée au survol */
}

.gallery-btn, .memories-btn {
  top: 10px;
}

.guestbook-btn, .contact-btn {
  bottom: 30px;
}

.gallery-btn, .guestbook-btn {
  left: 10px;
}

.memories-btn, .contact-btn {
  right: 10px;
}

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
  border-radius: 10px 10px 0 0;
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
  display: flex;
  flex-direction: column;
  align-items: center; /* Centre le contenu horizontalement */
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

/* Styles pour le cadre de la photo */
.photo-frame {
  position: relative;
  margin-top: 20px;
  width: 150px; /* Largeur du cadre */
  height: 150px; /* Hauteur du cadre */
  border-radius: 10px; /* Coins arrondis */
  overflow: hidden; /* Masque tout débordement */
}

.blur-frame {
  background: rgba(255, 255, 255, 0.2);
  position: absolute;
  top: 0;
  filter: blur(500px);
  width: 100%; /* S'ajuste à la largeur du cadre */
  height: 100%; /* Maintient le ratio d'aspect */
}

.photo {
  width: 100%; /* S'ajuste à la largeur du cadre */
  height: auto; /* Maintient le ratio d'aspect */
  filter: drop-shadow(0 0 15px rgba(255, 216, 230, 0.8)); /* Drop shadow céleste */
}

/* Header en bas pour mobile */
.header {
  position: fixed;
  bottom: 0;
  width: 100%;
}

/* Styles pour les écrans plus grands */
@media (min-width: 768px) {
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
  .home {
    border-radius: 0;
  }

  .hero-section {
    padding: 40px;
    max-width: 1440px;
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
