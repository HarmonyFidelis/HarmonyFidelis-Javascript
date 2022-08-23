# <ins>**Installation des gestionniaires de paquets** :<ins>

## <ins>Introduction de NodeJS et NPM :<ins>
<br>

NPM est le gestionnaire de paquets officiel de Node.js pour le langage Javascript. Sa maitrise est obligatoire pour tout developpeur voulant travailler dans cet environnement car il est present a toutes les etapes de la creation, du developpement et de la maintenance des applications Node.js.

C'est la qu'interviennent les gestionnaires de paquets : tels d'enormes annuaires, ils listent les paquets disponibles et permettent de les telecharger, installer, mettre a jour et desinstaller tres facilement.

Il existe de nombreux gestionnaires de paquets, chacun dedie a un langage ou a un framework particulier : Maven (JAVA), Bundler (Ruby), Composer (PHP).


## <ins>Introduction à YARN :<ins>
<br>

Yarn est complémentaire à npm car il permet d'optimisé le téléchargement multiple de fichier plutot que un à un comme le fait npm. Il permet donc d'optimiser le temps sur les gros projets, mais les commandes sont légérement différentes.

Yarn offre la possibilité d’installer un paquet malgré l’absence de connexion internet, à condition qu’il ait déjà été installé sur la machine auparavant.

Au fur et à mesure de l’avancement d’un projet, nous sommes souvent amenés à devoir installer de nouvelles dépendances, et le dossier node_modules devient rapidement un énorme fouillis.
Yarn offre la possibilité de comprendre rapidement la provenance de n’importe quelle dépendance présente dans node_modules.

Yarn permet également de mettre à jour une sélection de dépendances à travers une interface simple et clair.


## <ins>Installation NodeJS et NPM :<ins>
<br>

Rendez-vous sur [NodeJS](https://nodejs.org/fr/) et suivre le guide d'installation ! Suite à l'installation vous pourrez utilisé la function `npm`.

``` 
npm -v              // Version de npm
```

## <ins>Installation YARN :<ins>
<br>
Si vous avez installer NodeJS, dans votre Terminal
 
```code
corepack enable
```
 
puis : 
 
```code
npm i -g corepack
```
 
Si l'execution de script et bloquer dans powershell en mode administrateur :
 
```code
 set-executionpolicy unrestricted
```
 
## <ins>Commande NPM et Yarn :<ins>
<br>

### **Initiation d'un projet :**
| NPM | YARN | Description |
| :------- |:--------- | :---------------------- |
| npm init | yarn init |  Initiation d'un projet |
<br>

### **Installation des packages sur un projet importer avec GIT :**
| NPM | YARN | Description |
| :--------------------- | :---------------------------- | :--------------------------------------------- |
| npm i                  | yarn add                      |  Installation package en local production      |

### **Installation de package :**
| NPM | YARN | Description |
| :--------------------- | :---------------------------- | :--------------------------------------------- |
| npm i [nom_package]    | yarn add [nom_package]        |  Installation package en local production      |
| npm i [nom_package] -g | yarn global add [nom_package] |  Installation package en global production     |
| npm i [nom_package] -d | yarn add [nom_package]        |  package seulement nécessaire au developpement |

```
nom_package@1.2.3              // Permet de choisir la version à install
```
<br>

### **Desinstallation de package :**
| NPM | YARN | Description |
| :-------------------------- | :------------------------ | :----------------------------- |
| npm uninstall [nom_package] | yarn remove [nom_package] |  Supprime un package installer |
<br>

| NPM | YARN | Description |
| :-------------------------- | :------------------------ | :----------------------------- |
| npm update [nom_package] | yarn upgrade [nom_package]|  Mettre à jour un package |
<br>

### **Vérifier et corriger les vulnérabilités de votre projet :**
| NPM | YARN | Description |
| :-------------------------- | :------------------------ | :----------------------------- |
| npm audits | yarn audit |  Vérifie les vulnérabilités du projet |
| npm audits fix | yarn audit |  Vérifie les vulnérabilités du projet |
<br>

### **Executez un package**
| NPM | YARN | Description |
| :-------------------------- | :------------------------ | :----------------------------- |
| npm run [nom_package] | yarn run [nom_package] |  Vérifie les vulnérabilités du projet |
<br>

## <ins>Exemple de commande :<ins>
<br>

```code

npm init -y          // Initie un projet en rentrant des valeurs par défault
npm init             // Initie un projet en rentrant les valeurs(nom du project, version, ...)

npm i                // Install toutes les dépendance d'un projet
npm i sass           // Install préprocesseur sass en local
npm i sass -g        // Install préprocesseur sass en local
npm i cypress -d     // Install cypress pour le développement de test

npm uninstall sass   // Désinstalle le préprocesseur sass

npm update sass      // Mettre à jour le préprocesseur sass

npm audits           // Vérifira les vulnérabilités
npm audit fix        // Corrigera les vulnérabilités

npm run sass         // Execute le package sass

yarn init -y         // Initie un projet en rentrant des valeurs par défault
yarn init            // Initie un projet en rentrant les valeurs(nom du project, version, ...)

yarn add sass        // Install préprocesseur sass en local
yarn global add [nom_package] 

yarn remove sass     // Désinstalle le préprocesseur sass

yarn upgrade sass    // Mettre à jour le préprocesseur sass

yarn audit           // Vérifira les vulnérabilités

yarn run sass        // Execute le package sass

-- Option supplémentaire -- 

yarn why sass        // Donne des information sur le package et ses dépendance
yarn upgrade-interactive // Met à jour vos dépendance de maniére interactive

--- App

 |- node_modules
 |- .gitignore
 |- package.json
 |- readme.md
 |- yarn.lock

---

```


