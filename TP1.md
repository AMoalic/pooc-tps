Node.js 101
===========
Premier programme node
----------------------

- Ouvrir un terminal
- Vérifier que node.js est bien installé, exécutez ces commandes :  

```
$ node -v
```  
et ensuite   

```
$ npm -v
```  
Il faut que ces deux commandes vous renvoit quelque chose du type `v10.10.0` ou `6.4.1`  

- Rendez-vous dans votre dossier de travail (celui où vous allez mettre tous vos cours etc..) à l'aide de la commande `cd` (= change directory)
- Créez un dossier pour la POOC et pour le TP du jour :  

```
$ mkdir POOC  
$ cd POOC  
$ mkdir TP1  
$ cd TP1  
```
Voilà, vous êtes dans votre dossier de travail pour aujourd'hui.  

- créez un fichier `test.js` (à l'aide d'un éditeur de texte simple) dans ce dossier et écrivez :  

```
console.log('Hello, World');
```

- Retournez dans votre terminal et tapez la commande suivante :   

```
$ node test.js
```

Vous devriez voir apparaitre `Hello, World` à la suite de la commande.


Serveur node
------------
- Pour créer un serveur en node.js nous allons utiliser la bibliothèque  `express`, installez la avec cette commande :  

```
$ npm install express --save
```

- Créez un fichier `server.js` (toujours dans notre même dossier) avec comme contenu : 

```js
const express = require('express')
const app = express()
const port = 3000

app.get('/', (request, response) => {
  response.send('Requête reçue...')
})

app.get('/hello/:name', (request, response) => {
  response.send('Hello, '+request.params.name+'!');
})

app.listen(port, (err) => {
  if (err) {
    return console.log('Erreur du serveur : ', err)
  }

  console.log('Le serveur écoute sur le port '+port+'\nRendez vous sur http://localhost:'+port);
})
```

- Lancer le serveur avec la commande :
   
```
$ node server.js
```  

N'hésitez pas à ajouter d'autres chemin pour faire des tests. (Afficher la date du jour, prendre en compte plus de paramètres dans l'url etc...)


