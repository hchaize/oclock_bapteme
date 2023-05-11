# fetch

La méthode fetch est utiliser dans cas ou l’ou veut interagir avec une API REST.

Elle permet de faire des requêtes AJAX HTTP (requête sur des routes GET, POST… qui retourne du JSON), elle utilise des Promises, contrairement à la précédente méthode (XmlHttpRequest) qui utilisait des callback. C’est donc une méthode qui permet de faire des requête AJAX de façon moderne et plus intuitive.

Voici un exemple un peu théorique d’utilisation, on verra un exemple plus concret juste après, sur comment tu aurais pu l’utiliser dans le projet Skoule:

```jsx
fetch('https://api.example.com/data') // J'appelle la route que je veux requêter
.then(response => response.json()) // Si la requête aboutie, on lit le réponse en JSON
.then(data => console.log(data)) // On récupère les données demandées et on les affiche
.catch(error => console.error(error)); // S'il y a une erreur, on l'affiche

// Tu peux aussi utiliser la syntax Async/Await
```

Donc la c’est un cas basique, pour une route GET, mais comment faire pour une route POST ?

```jsx
let body = { // Je définis un objet bateau que j'utiliserai comme corps de ma requête
	firstname: "John",
	Lastname: "Doe",
	role: "admin"
};

fetch('https://api.example.com/user/create', { // J'appelle toujours la route
  method: 'POST', // Je définis la méthode de la requête que j'envoie
  headers: { // Je définis l'ensemble des header nécessaire à la requête (auth...)
    'Content-Type': 'application/json;charset=utf-8'
  },
  body: JSON.stringify(body) // Je transforme l'objet JS en chaine de caractères Json
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error(error));
```

Cette méthode fonctionne également avec une requête GET sauf qu’il n’y aura pas de body et que la méthode de la requête sera “GET”.

Maintenant un exemple plus concret pour le projet Skoule, tu aurais pu utiliser fetch pour supprimer les apprenants ou les profs sans à avoir à recharger la page entièrement.

Quand tu cliques sur le bouton de suppression d’un prof ou d’un apprenant, tu récupère son id et tu envoies une requête à la route de suppression, tu récupère le retour et s’il est concluant, tu supprime la ligne correspondante du DOM.

> Astuce: Tu peux même mettre un petit loader au moment du click sur le bouton, l’enlever au retour de la requête et mettre un petit toast indiquant que l’action s’est déroulée avec succès
> 

Je te laisse quelques liens pour approfondir le sujet:

[Fetch](https://fr.javascript.info/fetch)

[Utiliser Fetch - Référence Web API | MDN](https://developer.mozilla.org/fr/docs/Web/API/Fetch_API/Using_Fetch)

[Promise - JavaScript | MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Promise)

Et comme ouverture, je te laisse le lien vers la doc d’Axios, un client HTTP qui permet de faire des XMLHttpRequest, mais avec des Promises, et qui fonctionne aussi avec Node (côté Back)

[Introduction | Axios Docs](https://axios-http.com/fr/docs/intro)