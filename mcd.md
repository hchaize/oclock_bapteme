# mcd

Petite review concernant ton MCD:

À première vue, tu sembles avoir compris le concept, Bravo 🥳

Cependant tu as fais quelques petites erreurs:

- Dans le model MERISE, les relation doivent être hexagonal, ou en ellipse, les tiennent sont des rectangles (Je note tout de même l’effort de changer la couleur pour différencier)
- Sur l’ensemble de tes entités, il manque les identifiants permettant de les… identifier 🤡 (du moins ils sont là mais pas clairement identifiés comme le veut le model MERISE, soit avec un # devant ou en les soulignants)
- Concernant ta relation Many to Many LIKE, pas besoin de le préciser, les cardinalités sont faites pour ça (Clé étrangère ou table intermédiaire).
- En parlant des cardinalités, une erreur au niveau de la relation Many to Many LIKE, selon tes cardinalités, un user doit liker au minimum 1 produit et peut liker au maximum 1 produit, et un produit doit avoir au minimum un like d’un utilisateur et peut en avoir un seul au maximum. Le plus judicieux aurait été de dire qu’un utilisateur doit liker au minimum 0 produit et peut en liker n au maximum, et pareille pour les produits, il doit recevoir au minimum 0 like et peut en avoir au maximum n.

> D’ailleurs, rappel: Une relation Many to Many ne peut pas être définie par un 1 en cardinalité maximale, On ne peut avoir en cardinalités pour une Many to Many uniquement 0,n ou 1,n
> 

Voilà ! en corrigeant ces petites erreurs, le MCD devrait être parfaitement normé selon le model MERISE

Je te laisse quelques outils qui pourront t’aider dans la réalisation de MCD à l’avenir

- **GitMind**, entièrement gratuit est un très bon outil, téléchargeable, disponible partout même sur smartphone
- **LucidChart**, En ligne, gratuit pour une utilisation limitée
- **Draw.io**, En ligne, mais lui est complètement gratuit