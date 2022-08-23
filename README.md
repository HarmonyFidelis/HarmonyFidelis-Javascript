# JavaScript

---

---

## Table des matières

0.  [Introduction](#introduction)
1.  [Environnement](#environnement)
    1. [Gestionnaire de paquet NODEJS](#nodejs)
2.  [Javascript](#Javascript)
    1. [Javascript](#Javascript)
       1. [Javascript](#Javascript)

---

---

### Introduction

### 1. Environnement

---

#### <ins>1.1 PYCHARM : IDE Python</ins>

#### <ins>1.2 TERMINAL : Créer et naviguer à partir du projet </ins>

Pour pouvoir créer, supprimer ou encore naviguer dans un projet nous nous servons du terminal
Raccourcie IDE :

```
Commande TERMINAL :

mkdir name_directory                                // Permet de créer un dossier
touch file.js                                       // Permet de créer un fichier avec extension

rm name_directory                                   // Permet de supprimer un dossier
rm file.js                                          // Permet de supprimer un fichier

ls-la                                               // Permet de voir dossier et fichier à la racine

./file.js                                           // Execute le fichier

cd C:\path/directory/                               // Navigue dans le chemin indiquer
cd ./path/directory/                                // Navigue dans le chemin a partir du dossier racine
cd ../path/directory/                               // Recule d'un dossier et navigue dans le chemin indiquers
```

#### <ins>1.2 GIT : Versioning d'un projet</ins>

Nous pouvons à présent créer un projet et lui attribué une version et ainsi sauvegarde chaque avancé du projet avec
gestionnaire de version [GIT](https://git-scm.com/downloads)

```
Create PROJECT :

mkdir App                                           // Créer un dossier contenant le projet
cd ./App                                            // Naviguer dans ce dossier
git init                                            // Initialisation du versionning
touch .gitignore                                    // Permet d'ignoré fichier et dossier ne devant pas etre sauvegarder


Commande GIT :

git init                                            // Initialisation du versionning
git remote add https://github.com/path origin main  // Permet d'associer un projet à un repo distant
git clone https://github.com/path                   // Permet de recuperé un projet d'un repo distant
---
git add *                                           // Ajoute vaut modifications au commit
git commit -m "Message du commit"                   // Sauvegarde vos modifications avec un message des modifs apporter
git push                                            // Envois votre commit au repo distant
git pull                                            // Permet de récuperer les modifications apporté au repo distant
---
git branch name_branch                              // Permet de créer un branche secondaire de développement
git branch list                                     // Permet de voir les branches actives
git checkout name branch                            // Permet de naviger dans la branche
---
git merge                                           // !! Ajoute modifs de la branche secondaire dans la main !!
```

#### <ins>1.3 NodeJS : Installateur de paquets de Javascript</ins>

#### <ins>1.6 ARCHITECTURE : Architecture d'un projet</ins>

```text
    |-- LICENSE                                // Licence du projet
    |-- README.md                              // Documentation du projet
    |--.gitignore                              // Contient fichier à ignorer
    |-- fichier.js                             // Contient le programme
```

### <ins>2. LANGAGE DE PROGRAMMATION JAVASCRIPTS</ins>

---

#### <ins>2.0 IMPORT / EXPORT : Importez un paquet JavaScript</ins>
```
_IMPORTATION_
import name_function from "./path/name.extension";
import name_function from name_paquet;

_EXPORTATION_
module.export = name_variable;
module.export = name_function;

export let nameVariable = nameVariable1, nameVariable2;
export { name1, name2 };
export { variable1 as name1, variable2 as name2 };
export function nameFunction(){...}
export class nameClass {...}
```
#### <ins>2.0 TYPE DE DONNEES :</ins>
```
let name = "text";                       // String
let name = 10;                           // Number
let name = true;                         // Bool
let name = [Value, Value];               // Tableau
let name = [name:value, name:value];     // Dictionnaire
```

#### <ins>2.2 STOCKAGE DES DONNEES : Stocker vos données</ins>

```code
_COMMENTAIRE_
// Ceci est un commentaire
```
```code
_VARIABLE_
let name_variable = "valeur"                        // Variable contenant une donnée modifiable
print(name_variable)                                // response : "valeur"
print()

_CONSTANTE_
const NAME_CONSTANTE = "valeur"                     // Variable contenant une donnée non-modifiable
print(NAME_CONSTANTE)                               // response : "valeur"
```
```
_FUNCTION_

let name_function = (arg1) => {return this.arg1}    // Function fléchée

function name_function (arg1){return this.arg1}     // Function normale

async function(arg1){                               // Function async
    try{ let name = await arg1
    } catch(error){
        console.error(error);
    } finally {
        console.log("si exception execute code")
    }
}
```
```
_CLASS_

class NameClass {
    let count = 0

    constructor(attr1, attr2){
        this.name = "NameObject"
        this.attr1 = attr1;
        this.attr2 = attr2;
    }

}

const object1 = new nameClass("value", "value")
const object1 = new nameClass("value", "value")
const objectName = console.log(NameClass.name)
```
#### <ins>2.3 EXPRESSION</ins>
```
_EXPRESSION_
(valeur1 == valeur2)                  // Egalité
(valeur1 === valeur2)                 // Egalité stricte
(valeur1 !== valeur2)                 // Différent
(valeur1 !=== valeur2)                // Différent stricte
(valeur1 > valeur2)                   // Superieur
(valeur1 >= valeur2)                  // Superieur ou egal
(valeur1 <= valeur2)                  // Inferieur
(valeur1 <= valeur2)                  // Inferieur ou egal
```
#### <ins>2.3 CONDITION</ins>
```
_CONDITION_
if(condition){                      // Si la condition est true execute le code, mais si faux continue
    ...
} elseif(condition) {               // Sinon la condition est true execute le code, mais si faux continue
    ...
} else{                             // Sinon si toutes conditions false execute ce code
    ...
}

switch(value){                      // Reçois une valeur et si la valeur
    case x:                         // Exemple : si la valeur est x execute ce code
        ...
        break;                      // Puis arrete le code
    case y:                         // Exemple : si la valeur est y execute ce code
        ...
        continue;                   // Continue le code
    default:                        // Exemple : Si aucun valeur true alors execute ce code
        ...
        break;
}
```
#### <ins>2.4 BOUCLE</ins>
```
_FOR_
for(let i = 0; i < 10; i++){
    console.log(listName[i])
}

for(let i in listName ){
    console.log(listName[i])
}


for (let [key, value] of Object.entries(listName)) {
  console.log(`${key}: ${value}`);
}

_WHILE_
let i = 0

while(i < 5){                                // Repete tant que la condition et true
    i++;                                     // Mettre un incrémentation qui permet d'arreter la boucle
}

do{                                          // Repete jusqu'a ce que la condition soit false
    i++;                                     // Mettre un incrémentation qui permet d'arreter la boucle
}while(i < 5)
```


#### <ins>2.6 BOITE DE DIALOGUE</ins>

```
_BOITEDIALOGUE_
alert("message à afficher")                         // Permet d'afficher boite de dialogue

if(confirm("Souhaitez-vous confirmer ?")){          // Permet d'afficher boite de dialogue avec confirmation
    alert("Vous venez de confirmer !")
} else{
    alert("Vous venez de annulez")
}

prompt("Entrez votre age")                          // Permet d'afficher une boite de dialogue de type input
```


### <ins>3. DOM Document Objet Model

Le document va parcourir les éléments à partir de l'éléments racine, par défault celui-ci est <html></html>.

```code
|- document
    |- <html>
        |- <head>
            |- <title>
    |- <body>
        |- <h1>
        |- <p>
```

Pour lire un fichier DOM il vous faut simplement importer votre fichier JS dans la page HTML

```code
<script src="fichier.js" async defer></script>
```

#### <ins>3.1 RECUPARTION ELEMENT

Permet de recuperer les élementS choisit dans le fichier HTML

```code
_optionI_
let nameID = document.getElementById('nameID');                 // Récupére un ID
let nameClass = document.getElementsByClassName('nameClass');   // Récupére une Class
let baliseHTML = document.getElementsByTagName('nameBalise');   // Récupére element HTML
let nameAttribut = document.getElementsByName('nameAttribut');  // Récupére l'attribut

_optionII_
let nameID = document.querySelector('#nameID');                 // Récupére un ID
let nameClass = document.querySelectorAll('.nameClass');        // Récupére une Class
let nameBalise = document.querySelectorAll('nameBalise'):       // Récupére element HTML
let nameAttribut = document.querySelectorAll('nameBalise[src]');// Récupére l'attribut

_optionIII_
<div id="parent">
    <div id="previous"></div>
    <div id="main">
        <p>content</p>
    </div>
    <div id="next"></div>
</div>
<script type='text/javascript'>
    let main = document.querySelector("#main");                 // Selection un element(#main)
    let enfant = main.children;                                 // Selection enfant de main(p)
    let parent = main.parent;                                   // Selection le parent de l'élément(#parent)
    let precedent = main.previous                               // Selection precedent de l'élément(#previous)
    let suivant = main.next;                                    // Selection suivant de l'élément(#next)
</script>
```

#### <ins>3.2 AJOUT / MODIFIER / SUPPRIMER

```code
// HTML & TEXTUEL
const elementParent = document.createElement("div");            // Creation d'un nouvelle element(div)
elementParent.innerHTML = '<balise>texte</balise>';             // Creation d'un element HTML et TEXTUEL
elementParent.texteContent = 'texte';                           // Creation d'un TEXT

// ID
elementParent.id = 'nameID';                                    // Creation d'un ID

// CLASS
elementParent.classList.add('nameClass');                       // Creation d'une nouvelle class
elementParent.classList.contains('nameClass');                  // Retourne TRUE si la class existe
elementParent.classList.replace('oldClass', 'newClass');        // Remplace une class par une autre class
elementParent.classList.remove('nameClass');                    // Supprime class

// ATTRIBUT
elementParent.setAttribute('nameAttribut', 'valeur');           // Creation d'un attribut
elementParent.setAttribute('oldAttribut', 'newAttribut');       // Modifier le type d'attribut
elementParent.setAttribute('oldValeur', 'newValeur');           // Modifier la valeur de l'attribut

// STYLE
elementParent.style.namestylecss = "valeur";                    // Creer un element style
elementParent.style = "namestyle:valeur; namestyle:valeur;";    // Creer des elements style
_
```

#### <ins>3.3 PARENTAGE & PLACEMENT

```code
// ENFANT
elementParent.appendChild(elementEnfant);                       // Ajoute elementEnfant a elementParent
elementParent.removeChild(elementEnfant);                       // Supprimer elementEnfant de elementParent
elementParent.replaceChild(oldEnfant, newEnfant);               // Remplace un elementEnfant de element parent

// PLACEMENT
elementParent.insertBefore(elementAAjouter, elementEnfant);     // Insertion elementAAjouter avent elementEnfant
elementParent.insertAdjacentHTML(position, elementAAjouter);    // Insertion de l'element HTML a la position choisit
elementParent.insertAdjacentText(position, elementAAjouter);    // Insertion de l'element TEXT a la position choisit
elementParent.insertAdjacentElement(position, elementAAjouter); // Insertion de l'element ELEMENT a la position choisit

// POSITION POSSIBLE
beforebegin                                                     // Avent que elementEnfant commence
afterbegin                                                      // Apres que elementEnfant commence
beforeend                                                       // Avent que elementEnfant finisse
afterend                                                        // Apres que elementEnfant finisse
```

---

### <ins>4. AJAX / Fetch (Appel d'API)

AJAX (Asynchronous JavaScript + XML)
