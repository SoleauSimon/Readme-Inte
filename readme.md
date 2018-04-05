# Documentation


## Convention BEM
* B -> Block
* E -> Element
* M -> Modifier

```HTML
<!-- __mainList = Block-->
<ul class="mainList mainList-xmas">
  <!-- __item = Element-->
  <li class="mainList__item">
    <!-- __itemLink = Element-->
    <a class="mainList__itemLink mainList__itemLink--isActive"href="/home">Home</a>
  </li>
  <li class="mainList__item">
    <!-- __itemLink = Element-->
    <a class="mainList__itemLink"href="/home">About</a>
  </li>
  <li class="mainList__item">
    <!-- __itemLink = Element-->
    <a class="mainList__itemLink"href="/home">Works</a>
  </li>
</ul>
```
```CSS
.mainList {
  display: flex;
  justify-content: space-between;
  &--xmas {
    background: green;
  }
  &__item {
    list-style: none;
  }
  &__itemLink {
    color: red;
    &--isActive {
      color: white;
    }
  }
}
```

## Pseudo attributs

Les pseudo attributs `before` et `after` permettent de créer des noeux HTML et CSS.
Ils sont généralement utiliser pour ajouter des ornements, des décorations ... On
peut bien entendu faire des animations avec, les positionner par rapport à leurs
parents (relative / absolute) **Ils doivent obligatoirement avoir un `content: ''`**
afin de s'afficher.

```HTML
<section>
  <h1 class="cover__mainTitle">Présentation des pseudo-attributs</h1>
</section>
```
```CSS
.cover {
  background: #FDFDFD;
  padding: 20px;
  &__mainTitle {
    text-align: center;
    font-size: 24px;
    color: green;
    position: relative;
    &::before,
    &::after {
      position: absolute;
      content: '';
      width: 50px;
      height: 50px;
      background: green;
    }
    &::before {
    left : 0;
    }
    &::after {
      right: 0;
    }
  }
}
```

## REM, EM, %, VW Sizing

### %

### EM

```CSS
.cover {
  font-size: 100%; /* 100% = 16px */
  &__mainTitle {
    /* 1.6em === 16px */
    font-size: 1.6em;
    /* 32rem === 320px */
    width: 32rem;
  }
}
```

### REM

* Le REm est basé sur la taille de la racine (soit la balise <html>) qui, par
défaut à une valeur de 16px. Afin d'éviter tout calcul, il est nécessaire de
l'écraser  en donnant une base de 10px soit 62,5%.
* Le REM est intéraissant à utiliser si les media-queries emplyées sont en REM
également. Cela vous permettra de garder des proportions égales lorsqu'on va
redimensionner la page.
* Ses proportions seront également gardées quand l'utilisateur zoomera dans
votre page.

```CSS
html 
  font-size: 62,5%;
}
```

### VW(idth) / VH(eight)

* Unités relatives à la taille de votre écran (peu importe le device)
* Attention au VH et à son contenu. 100vh === 100vh quoi qu'il arrive
* VW : très utile pour les interfaces fluides.

## Liens utiles :
## Installer parcel

* Installer node.js et homebrew
* Aller dans un dossier de développement
* mkdir parcel-boilerplate
* cd parcel-boilerplate
* npm -v
* npm init > name = parcel-boilerplate > author = Simon
* ll
* sudo npm install -g parcel-bundler
**installer yarn si sa marche pas**
* touch index.html index.js
➜  parcel-boilerplate git:(master) ✗ mkdir styles
➜  parcel-boilerplate git:(master) ✗ cd styles
➜  styles git:(master) ✗ touch styles.scss
➜  styles git:(master) ✗ ll
total 0
-rw-r--r--  1 simonsoleau  staff     0B 27 fév 14:38 styles.scss
➜  styles git:(master) ✗ cd ..
➜  parcel-boilerplate git:(master) ✗ ll
* yarn OU npm install
* yarn start OU npm start
* cd styles
* mkdir global && mkdir components && mkdir mixins
* cd global
* touch _variables.scss && touch _reset.scss
* touch mixins/_forsize.scss
* ➜  global git:(master) ✗ cd ..
➜  styles git:(master) ✗ touch mixins/_forsize.scss
➜  styles git:(master) ✗ touch components/_header.scss
➜  styles git:(master) ✗ touch global/_reset.scss
➜  styles git:(master) ✗ touch global/_variables.scss
* touch .postcssrc
* npm install auto prefixer(Pour les npm)
* yarn add autoprefixer (Pour Yarn)
* dans postcssrc > mettre 
{
  "plugins": {
    "autoprefixer": {
      "browsers": [">1%", "last 4 versions", "Firefox ESR", "not ie < 9"],
      "flexbox": "no-2009",
      "grid": true
    }
  }
}
* touch .babelrc
* Pour npm > nmp install -D babel-preset-env OU yarn add -d babel-preset-env
{
  "presets": [
     ["env", {
      "targets": {
        "browsers": ["last 2 versions", "safari >= 7"]
      }
    }]]
}
* test si ça marche
* mkdir src, mv styles src / index.js src / index.html src et changer package.json main/ start / build et y mettre src
* 


## Github
git init
touch .gitignore (On met dedans ce que l'on veut ignorer)
git status
git add .
git commit -m "Mon message"
#Liens utiles

* https://github.com/h5bp/Front-end-Developer-Interview-Questions

* http://cssnext.io/

#MYSQL

```mysql
create table `kandt-pages`.`pages-content`(
`id` INT UNSIGNED NOT NULL AUTO_INCREMENT,
  `page`       varchar(110),
  `title`      varchar(70),
  `h1`         varchar(3000),
  `p`          varchar(100),
  `span-class` varchar(50),
  `span-text`  varchar(100),
  `img-alt`    varchar(2048),
  `img-src`    varchar(30),
  `nav-title`  varchar(100),
  primary key (`page`)
);
```

mysql.server start --skip-grand-tables (Mode YOLO)