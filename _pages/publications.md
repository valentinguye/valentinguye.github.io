---
layout: page
permalink: /Publications/
title: Publications
nav: true
nav_order: 2
---
If you cannot access papers, code or data, do not hesitate to reach out, I am happy to share what I can. 

<h2 class="pub-section">Peer-reviewed articles</h2>
{% bibliography --file papers %}

<h2 class="pub-section">Policy briefs</h2>
{% bibliography --file policy-briefs %}

<h2 class="pub-section">Datasets</h2>
{% bibliography --file datasets %}

<style>
  /* Image à droite au lieu de gauche */

.row > .col.abbr {
  order: 2;
}
.row > .col-sm-8[id] {
  order: 1;
}
/*explication : order: 2 / order: 1 : comme .row est en display: flex (grille Bootstrap), on peut simplement inverser l'ordre visuel des deux colonnes sans toucher au HTML généré — la colonne image passe après la colonne texte.  */
  
/* Image plus grande */
.row > .col.abbr {
  flex: 0 0 260px;
  max-width: 260px;
}
/* remplace la largeur imposée par col-sm-2 (assez étroite) par une largeur fixe plus généreuse. Ajustez 260px selon le rendu (essayez 220px, 300px... selon votre goût).  */
.row > .col.abbr .preview {
  width: 100%;
  height: auto;
}
/*force l'image à occuper toute la largeur de sa nouvelle colonne, plutôt que sa taille d'origine.  */

  /* La ligne s'agrandit naturellement avec l'image plus grande,
   mais on ajoute un peu de marge verticale pour l'aération */
.row {
  margin-bottom: 1.5rem;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function () {
  document.querySelectorAll('a.abstract.btn').forEach(function (btn) {
    btn.textContent = 'abstract';
    btn.addEventListener('click', function (e) {
      e.preventDefault();
      var container = btn.closest('[id]') || btn.parentElement;
      var abs = container ? container.querySelector('div.abstract') : null;
      if (abs) {
        abs.classList.toggle('open');
        abs.classList.toggle('hidden');
      }
    });
  });

  document.querySelectorAll('.links a.btn').forEach(function (btn) {
    if (btn.textContent.trim() === 'HTML') {
      btn.textContent = 'link';
    }
  });
});
</script>
