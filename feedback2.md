# feedback2

## 2 - Lister tous les profs

Cela fonctionne globalement

L’affichage de la page est sur toute la largeur, ce qui n’est pas esthétique et ce qui rend compliquer la lecture des menus déroulants pour la suppression.

Utilisant bootstrap, tu aurais pu mettre tout ton code dans un container

- Ouverture d’une div dans ton template header
- et fermeture de celle-ci dans ton template footer

Comme ça toutes tes views auraient été dans un container et tu n’aurais plus eu à t’en soucier.

[Containers](https://getbootstrap.com/docs/5.0/layout/containers/)

---

## 3 - Lister tous les étudiants

De même que précédement, cela fonctionne globalement, les remarques sont les mêmes.

---

## 4 - Ajouter un prof

Globalement cela ne fonctionne pas, mais on en est pas loin 💪

Il n’y a pas de bouton d’ajout, on accède à l’interface d’ajout via les boutons d’édition, il aurait fallu faire un bouton global au dessus de la liste.

L’envoi du formulaire ne donne rien, il manque une méthode d’insert dans la classe Teacher, et le controller POST qui va avec

---

## BILAN

Beaucoup de points n’ont pas été traité, peut-être des blocages ? Dans ce cas, il ne faut pas rester bloquer et aller chercher de l’aide extérieur. C’est dommage car ce qui est fait est globalement bien fait. Fait attention également, il y a des petites erreurs d’indentation dans certaines classes, ce qui rend la lecture du code difficile.