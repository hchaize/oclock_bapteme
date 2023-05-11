# feedback4

Le projet ne fonctionne pas

Une erreur mentionne l’absence du MainController, avec ce genre d’erreur deux solutions:

- Supprimer toutes les utilisation de ce fichier
- Intégrer ce fichier

En incluant le fichier et en relançant le script, une autre erreur apparait, on avance c’est bien: Absence du CoreController, si on suit la logique au dessus, on l’inclu aussi (d’autant plus que tous tes controller sont des extension de ce controller).

Concernant le code:

Il manque des point-virgules à la fin de beaucoup de ligne; des erreur dans le nom des variables; l’instanciation d’une classe n’est pas maitrisé (Cf. StudentController et TeacherController):

```php
$student = new Student();
// Et non pas
$studentsModel = new Students
students();
```

Les méthodes static doivent être appelés statiquement (CLASSE::METHODE) (Cf. StudentController et TeacherController)

```php
$students = Student::findAll();
// Et non pas
$students = $studentsdModel->findAll();
```

(Rappel: une méthode static est une méthode qui peut importe l’instance d’une même classe renverra toujours la même valeur, donc pas besoin d’instancier de classe)

[PHP: Statique - Manual](https://www.php.net/manual/fr/language.oop5.static.php)

Je peux voir que tu as inclu un fichier composer.phar à la racine de ton projet, saches que tu n’en as pas besoin si composer est correctement installer sur ton poste.

Je peux voir aussi que tu as placer les fichiers sql dans le dossier Utils, as-tu réussi à importer la base ? Car le fait que tu places ces fichiers ici me met un doute, ils ne représente pas la base en tant que tel mais un moyen pour la créer et d’importer les données

## BILAN

Les bases doivent être revu, cependant ne soit pas découragé, fixe toi une méthodologie, avance point par point, demande une aide externe. Ne laisse pas passer les erreurs et fix les petit à petit. Retravaille les connaissances de base, les notions MVC, les controlleur, les classes, les variables, les points-virgules etc. et petit à petit tu devrais t’en sortir et arriver à progresser.