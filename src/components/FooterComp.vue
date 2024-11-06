<template>
  <footer :class="{'footer-bottom': isHeaderBottom, 'footer-top': !isHeaderBottom}">
    <div class="footer-content">
      <p>&copy; {{ currentYear }} | Pedro Costa. Tous droits réservés. </p>
      <p> Créé avec amour pour honorer la mémoire.</p>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

const currentYear = ref(new Date().getFullYear());
const isHeaderBottom = ref(false); // Cette valeur sera déterminée par le parent

// Fonction pour mettre à jour l'état si nécessaire
const setHeaderPosition = (isBottom) => {
  isHeaderBottom.value = isBottom;
};
</script>

<style scoped>
footer {
  width: 100%;
  height: 5vh; /* Ajustez la hauteur du footer */
  background: #181818; /* Couleur de fond sombre */
  color: #FFD700; /* Couleur dorée pour le texte */
  display: flex;
  align-items: center;
  justify-content: center; /* Centre le contenu horizontalement */
  box-shadow: 0 -2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.footer-bottom {
  position: fixed;
  bottom: 0; /* Positionne le footer en bas de l’écran */
}

.footer-top {
  position: fixed;
  top: 0; /* Positionne le footer en haut de l’écran */
}

.footer-content {
  text-align: center; /* Centre le texte dans le footer */
}

.footer-content p {
  margin: 0; /* Élimine le margin par défaut */
  font-size: 1rem; /* Taille de police pour le texte */
  letter-spacing: 1px; /* Espacement entre les lettres */
}

/* Styles responsives pour desktop */
@media (min-width: 1025px) {
  .footer-content{
    display: flex;
  }
  .footer-bottom {
    position: relative; /* Change pour relative afin de ne pas être fixe en bas */
    height: 10vh; /* Augmente la hauteur pour desktop si nécessaire */
    margin-top: 15vh; /* Espace pour le contenu principal si nécessaire */
  }

  .footer-top {
    position: relative; /* S'assure que le footer en haut est également relatif */
  }
}
</style>
