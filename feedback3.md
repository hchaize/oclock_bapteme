# feedback3

## ROUTES

Il y a pleins de problème de routing, quand on est sensé tomber sur la page d’accueil, on tombe sur une erreur 404, avec un lien vers une route /home.

Dans la navbar, pleins d’erreur au niveau des routes, qui se finisse par .html, ça ne peut donc pas fonctionner correctement. Je te conseil de revoir le fonctionnement des routes.

[AltoRouter - PHP Router that supports REST, dynamic and reversed routing](https://altorouter.com/)

## 2 - Lister tous les profs

La liste fonctionne, cependant plusieurs choses sont à revoir.

Le lien dans la navbar fonctionne, mais arrivé sur l’interface, elle disparait. Tu aurais du définir un layout pour toute tes views (header et footer globaux)

[Créez un template de page](https://openclassrooms.com/fr/courses/4670706-adoptez-une-architecture-mvc-en-php/7848103-creez-un-template-de-page)

Garde bien en tête que tu peux définir des bouts de view pour les réutiliser d’une route à l’autre pour éviter de dupliquer du code inutilement.

La liste prend toute la largeur de la page, ce qui n’est pas très esthétique. Utilisant bootstrap, et si tu avais définit un layout, tu aurais pu mettre toute tes interface dans un container bootstrap, en ouvrant un div dans la partie header et en la fermant dans le footer, comme ça tu n’avais plus à t’en soucier.

[Containers](https://getbootstrap.com/docs/5.0/layout/containers/)

## 3 - Lister tous les étudiants

C’est la même chose que pour la liste des profs.

## 4 et 5 - Ajouter un prof et un élève

Cela ne fonctionne pas, et pourtant on est pas loin du but.

Quand on clique sur le bouton ajouter au niveau de la liste des profs, cela nous ramène vers le formulaire d’ajout d’un étudiant 😅 peut-être le résultat d’un copié-collé pour des tests (méthode studentAdd() dans le TeacherController), ou alors n’as tu pas compris la logique, et dans ce cas il ne faut pas hésiter à demander une aide externe.

Concernant le formulaire, les valeurs pour le select “prof” sont mise en dur dans la view, ce qui ne peut pas fonctionner si tu viens à ajouter d’autres profs, et ce qui ne fonctionne pas actuellement, ce qui te retourne une erreur SQL car ta base attend forcément une valeur correcte pour prof. Dans ton controller tu aurais du récupérer la liste des profs avec la formule “Teacher::findAll()”, la passer à la view et en faire le rendu côté view.

En tout cas, ne te mélange pas les pinceaux, implémente chaque interface indépendamment, sépare bien ce qui est du ressort des profs et des élève, et tu verras plus tard pour factoriser si tel est ton but.

## BILAN

Des progrès à faire avec le fonctionnement de l’architecture MVC de manière générale, notamment la liaison Controller / View, et au niveau du routing.

Pour info, j’ai du importer un .htaccess dans ton dossier public pour que le projet puisse fonctionner, peut-être as tu oublier de le committer ?