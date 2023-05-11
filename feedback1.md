# feedback1

## 2 - Lister tous les profs

Globalement, cela fonctionne très bien ! l’affichage est propre 😀.

La méthode findAll de la classe Teacher est déclarer en static, il faut donc l’appeler statiquement (CLASSE::METHODE)

```php
Teacher::findAll();
```

Une méthode static renvoie la même chose pour n’importe quelle instance d’une même classe.

Ex: Peut importe quel Teacher est instancié, la méthode findAll() retournera la liste des profs, et donc pas besoin d’instancier un Teacher.

Je te donne le lien vers la doc pour plus d’infos

[PHP: Statique - Manual](https://www.php.net/manual/fr/language.oop5.static.php)

---

## 3 - Lister tous les étudiants

Fonctionnellement et visuellement, c’est OK 👌.

Même remarque que pour l’étape précédente mais avec la classe Student. 

On voit que le code a été réutilisé entre les deux controllers. L’étape d’après serait de factoriser pour éviter la duplication du code.

---

## 4 - Ajout d’un prof

La fonctionnalité est implémentée et fonctionnelle 👏

Tu vérifie que $_POST contient bien des données, mais tu utilise après la fonction filter_input, qui fonctionne très bien ! Mais qui ne rend pas très clair la compréhension du code, et qui ne sers pas a grand chose dans la majorité des données, tu n’appliques aucun filtre dessus. 

### Remarque

Tu aurais pu conserver les valeur entrées dans le formulaire en cas ou celui-ci ne passe pas, cela évite de tout réécrire

---

## 5 - Ajout d’un étudiant

Ça fonctionne comme précédemment, le code est le même 👍 L’étape suivante serait de factoriser pour éviter la duplication du code (comme pour les listes)

---

## 6 - Restreindre l’accès

Dans la globalité, cela fonctionne, les checks sont faits, cependant deux petits couak:

- Un utilisateur désactivé peut se connecter
- l’accès à la page “Home” n’est pas restreint (mais je note l’effort d’adapter la navbar)

---

## 7 - Mettre en place les permissions

Les permissions sont gérées, c’est fonctionnel. Un petit oubli, le rôle “user”, n’a pas accès à la liste des profs (oublie d’inclure le rôle dans le tableau $acl du CoreController).

---

## BONUS

### Validation des données

Tout est bon 🥳, sauf la validation du status. En effet tu le passe dans une fonction filter_input pour n’en sortir que les entier, mais la valeur doit être limité à 1 ou à 2, et dans ce cas, tous les entiers sont valide. Tu aurais pu ajouter à cela une condition pour vérifier la valeur de status.

---

### Modification d’un prof et d’un étudiant

Cela ne fonctionne pas…. Mais on est pas loin de la vérité !

En effet le formulaire dans la view a une propriété action dont la route n’est pas correcte, donc te redirige vers un 404, car la route que tu demandes de générer demande un id (l’id du prof ou de l’étudiant à modifier), en ajoutant l’id au générateur de route dans ta propriété action, cela fonctionne:

```php
$router->generate('nom_de_ta_route', ['studentid' => $student->getId()]);
```

Et du coup même chose pour le côté profs.

---

### Suppression d’un prof et d’un étudiant

C’est parfait 🥳

---

## MEGA BONUS

Tu as traité un sur les deux méga bonus

### Utilisateur

Tu as eu le temps de traiter ce bonus seulement en partie.

Tu as intégré la liste des utilisateur mais aucune action n’est possible.

Donc concernant la liste même remarque que pour les deux autres liste (méthode static et factorisation)

---

## BILAN

C’est du très bon travail dans l’ensemble, j’ai par contre eu un soucis pour regarder ton projet, en effet il manquait un .htaccess, peut-être as-tu oublié de le committer ?