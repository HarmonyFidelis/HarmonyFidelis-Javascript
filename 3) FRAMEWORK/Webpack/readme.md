# Webpack

---

## Installation

---

- Créez un fichier JSON

```text
npm init -y
```

- Installez webpack

```text
npm i webpack webpack-cli --save-dev
```

### Création de répertoires

- Créer les répertoires et fichier manquant

```text
    |-- node_modules
    |-- src
        |-- fonts
            |-- roboto.ttf
        |-- images
            |-- 100890.jpg
        |-- public
            |-- index.html
        |-- style
            |-- sass
            |-- style.css
            |-- style.scss
        |-- index.js
    |--.gitignore
```

### Executez webpack

```text
npx webpack --mode development
```

---

## Configuration - HTML

---

### Modifier le fichier package.json

Dans le fichier package.json modifier la partie script

```code
  "scripts": {
    "dev": "webpack --mode development",
    "build": "webpack --mode production"
  },
```

### Créer fichier webpack.config.js

A la racine du projet créer le fichier webpack.config.js

```code
    |-- webpack.config.js
```

### Installez html-webpack-plugin

Installez html-webpack-plugin qui va permettre de générer automatiquement vos fichiers html

```code
npm install html-webpack-plugin --save-dev
```

### Modifier webpack.config.json

```code
const HtmlWebpackPlugin = require("html-webpack-plugin");
const path = require("path");

module.exports = {

  //Webpack config
  entry: {
    main: path.resolve(__dirname, "./src/index.js"),
  },
  output: {
    filename: "[name].bundle.js",
    path: path.resolve(__dirname, "dist"),
  },

  // HTML
  plugins: [
    new HtmlWebpackPlugin({
      title: "Titre du site",
    }),
  ],
};

```

---

## Configuration - Serveur

---

### Installez webpack-dev-server

Installez webpack-dev-server qui va permettre de générer un serveur local

```code
npm install webpack-dev-server --save-dev
```

### Modifier webpack.config

```code
const HtmlWebpackPlugin = require("html-webpack-plugin");
const path = require("path");

module.exports = {
  //Webpack config
  entry: {
    main: path.resolve(__dirname, "./src/index.js"),
  },
  output: {
    filename: "[name].bundle.js",
    path: path.resolve(__dirname, "dist"),
  },

  // Server
  devServer: {
    static: {
      directory: path.join(__dirname, "./dist"),
    },
    compress: true,
    port: 9000,
  },

  // HTML
  plugins: [
    new HtmlWebpackPlugin({
      title: "Titre du site",
    }),
  ],
};
```

### Modifier package.json

```code
  "scripts": {
    "dev": "webpack serve --mode development",
    "build": "webpack --mode production"
  },
```

### Executez server avec les modifications

```code
npm run dev
```

### Accedez au serveur

[http://localhost:9000](http://localhost:9000/)

---

## Configuration - Transpileur

---

Un transpileur permet de rendre votre code compatible avec tous les navigateurs et optimise le code.

### Installation de babel

```code
npm i babel-loader @babel/core @babel/preset-env --save-dev
```

### Configuration de babel

Dans webpack.config.js

```code
...

  // HTML
  plugins: [
    new HtmlWebpackPlugin({
      title: "Titre du site",
      template: "./src/public/index.html",
      filename: "index.html", // output file
    }),
    ],

  // Babel
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ["@babel/preset-env"],
          },
        },
      },
    ],
  },

```

### Créer un nouveau fichier component.js

```code
    |-- src
        |-- component.js
```

### Modifier le fichier component.js

```text
const component = () => {
  const element = document.createElement("h2");
  element.innerHTML = "Webpack DOM dans component.js";
  return element;
};

export default component;
```

### Import component.js dans app.js

```code
console.log("Webpack is ready !");

//import composant
import component from "./component";

//Lis le composant
document.body.appendChild(component());

```

---

## Configuration - Style

---

- sass-loader – pour la compilation SCSS et CSS
- node-sass – pour node sass
- postcss-loader - Traiter CSS avec PostCSS
- css-loader – résoudre les importations CSS
- style-loader – injecter du CSS dans le Dom

### Installation des chargeurs de style

```code
npm i sass-loader postcss-loader css-loader style-loader postcss-preset-env node-sass --save-dev
```

### Créer fichier postCSS.config.js

A la racine créer postCSS.config.js

```code
    |-- postCSS.config.js
```

Modifier postCSS.config.js

```code
    module.exports = {
  plugin: [
    [
      "postcss-preset-env",
      {
        // options
      },
    ],
  ],
};

```

### Modifier webpack.config.js pour le style

```code
// Babel
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ["@babel/preset-env"],
          },
        },
      },
      {
        test: /\.(scss|css)$/i,
        use: ["style-loader", "css-loader", "sass-loader", "postcss-loader"],
      },
    ],
  },
```

### Import style dans app.js

```code
console.log("Webpack is ready !");

//import composant
import component from "./component";

//import style
import "./style/style.css";

//Lis le composant
document.body.appendChild(component());
```

Créer un background-colors pour essayer. Dans .src/style/style.css

```code
body {
  background-color: red;
}
```

---

## Configuration - Image

---

### Installation file-loader

```code
npm i file-loader --save-dev
```

### Configuration file-loader dans webpack.config.js

```code
// Babel
  module: {
    rules: [

      // babel
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ["@babel/preset-env"],
          },
        },
      },

      // style
      {
        test: /\.(scss|css)$/i,
        use: ["style-loader", "css-loader", "sass-loader", "postcss-loader"],
      },

      // images
      {
        test: /\.(?:ico|gif|png|svg|jpg|jpeg)$/i,
        loader: "file-loader",
        options: {
          name: "/assets/images/[name].[ext]",
        },
      },
    ],
  },
```

Mettre une image au bon format dans src/images/

```code
  |-- src
    |-- images
      |-- test.png
```

### Import votre image dans app.js

```code
// import votre image
import testImage from "./images/test.png";
const img = document.createElement("img");
img.src = testImage;
document.body.appendChild(img);
```

---

## Configuration - Fonts

---

### Installation url-loader

```code
  npm i url-loader --save-dev
```

### configuration url-loader

Dans webpack.config.js

```code
      // images
      {
        test: /\.(?:ico|gif|png|svg|jpg|jpeg)$/i,
        loader: "file-loader",
        options: {
          name: "/assets/images/[name].[ext]",
        },
      },
      // fonts
      {
        test: /\.(woff|woff2|eot|ttf|otf)$/i,
        loader: "url-loader",
        options: {
          limit: "50000",
          mimetype: "application/font-ttf",
          name: "/assets/fonts/[name].[ext]",
        },
      },
```

### Utiliser fonts dans fichier .css

```code
@font-face {
  font-family: 'Open Sans';
  font-style: normal;
  font-weight: normal;
  src:
    url('./assets/fonts/OpenSans-Regular.woff2') format('woff2'),
    url('./assets/fonts/OpenSans-Regular.woff') format('woff');
}

html,
body {
  font-family: 'Open Sans', sans-serif;
}
```

### Utiliser fonts dans fichier .js

```code
import OpenSansRegularWoffTwo from './assets/fonts/OpenSans-Regular.woff2';
import OpenSansRegularWoff from './assets/fonts/OpenSans-Regular.woff';

const myGlobalCSS = `
  @font-face {
    font-family: 'Open Sans';
    font-style: normal;
    font-weight: normal;
    src:
      url('${OpenSansRegularWoffTwo}') format('woff2'),
      url('${OpenSansRegularWoff}') format('woff');
  }

  html, body {
    font-family: 'Open Sans', sans-serif;
  }
`;
```
