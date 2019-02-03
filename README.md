# Lib builder

**Lib builder** est un bundle de modules JavaScript open source. Il permet de regrouper des modules javascript en un seul module javascript (umd).

## Installation
```
npm install lib-builder -g
```
## Fichier de configuration
build.js
```typescript
module.exports  = {
	"main":  "string",// fichier de point d'entrée. ex : "lib/index.js"
	"out":  "string", // fichier de sortie. ex : "dist/bundle.js"
	"config": {
		"name":  "string", // nom de la librairie si elle est chargée de manière globale. ex : "MyLib",
		"path": [ // Liste des entrées de mappage des chemins d'accès.
			{ 
				test: "Regex", // regex permettant de savoir si le chemin doit être ré-écrit. ex : /^(lib\/*)/ 
				result: "string" // règle de ré-écriture du chemin. ex : "/node_modules/$1"
				// Pour l'exemple précédent le chemin "lib/mylib/index.js" sera ré-écrit en "/node_modules/mylib/index.js"
			}
		]
	}
}
```
## Commande
```
libuilder
```
ou
```
libuilder build.js
```