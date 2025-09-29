# Cours Web – Licence 1 Informatique

## Table des matières
# Sommaire du cours Web – Licence 1 Informatique

## 1. Introduction au Web
- [Qu’est-ce que le HTTP ?](#quest-ce-que-le-http-)
- [Serveur Web](#serveur-web)

## 2. Internet et le Web
- [Historique et ARPANET](#historique-et-arpanet)
- [FAI et Systèmes Autonomes](#fai-et-systèmes-autonomes)
- [Web ≠ Internet](#web--internet)
- [Navigateur et HTTP](#navigateur-et-http)

## 3. HTTP en détail
- [Principe Client / Serveur](#principe-client--serveur)
- [Protocole sans état](#protocole-sans-état)
- [Codes de statut HTTP](#codes-de-statut-http)

## 4. Cookies

## 5. Serveurs Web et Hébergeurs

## 6. DNS et URL
- [DNS](#dns)
- [URL (absolue / relative)](#url)

## 7. HTML
- [Structure d’un document](#structure-dun-document)
- [Balises et attributs](#balises-et-attributs)
- [Listes, liens et tableaux](#listes-liens-et-tableaux)
- [Multimédia et accessibilité](#multimédia-et-accessibilité)
- [Catégories de balises et accessibilité](#Partie-HTML-et-CSS-Cours-Détaillé)
- [Formulaire html](#formulaire-html)

## 8. CSS
- [Fonctionnement des règles](#fonctionnement-des-règles)
- [Sélecteurs](#sélecteurs)
- [Modèle de boîte (Box Model)](#modèle-de-boîte-box-model)
- [Types d’affichage : block, inline, inline-block](#types-daffichage-block-inline-inline-block)
- [Flexbox](#flexbox)
- [Responsive Design](#responsive-design-media-queries-unités-relatives-images-adaptatives)

## 9. Bibliothèques CSS et JavaScript
- [Comment choisir sa bibliothèque](#comment-choisir-sa-bibliothèque)
- [CDN (Content Delivery Network)](#cdn-content-delivery-network)
- [Bootstrap](#bootstrap)
  - [Conteneur, ligne et colonne](#conteneur-ligne-et-colonne)
  - [Classes responsive](#classes-responsive)
  - [Couleurs](#couleurs)
  - [Marges et padding ltr-rtl](#marges-et-padding-ltr-rtl)

## 10. Programmation Web Dynamique
- [Interprétation côté serveur](#interpretation-cote-serveur)
- [Serveurs web et moteurs d'exécution](#serveurs-web-et-moteurs-dexecution)
- [Packs tout-en-un pour développement local](#packs-tout-en-un-pour-developpement-local)

## 11. Gestionnaire de base de données (SGBD)
- [Rôle et utilité](#role-et-utilite)
- [Types de bases de données](#types-de-bases-de-donnees)
  - [Relationnelle SQL](#relationnelle-sql)
  - [Non relationnelle NoSQL](#non-relationnelle-nosql)
- [Schéma de fonctionnement client-serveur-base de données](#schema-de-fonctionnement)


---

## Introduction au Web

### Qu’est-ce que le HTTP ?
- **HTTP (HyperText Transfer Protocol)** permet d’échanger des documents multimédias.
- Fonctionne sur un modèle **client / serveur** :
  - Le **client** (navigateur) envoie une requête.
  - Le **serveur** traite la requête et renvoie une réponse.
- **Sans état** : le serveur ne garde pas en mémoire les requêtes précédentes.
- Exemple d’en-tête :
```

Connection: keep-alive

```

### Serveur Web
- Application capable de répondre à des requêtes HTTP.
- Couplé à :
- Un **moteur de script** (PHP, Node.js…)
- Un **SGBD** (MySQL, PostgreSQL…)
- Exemples : Apache, Nginx, IIS.
- Distributions complètes :
- **WAMP** (Windows + Apache + MySQL + PHP)
- **LAMP** (Linux + Apache + MySQL + PHP)

---

## Internet et le Web

### Historique et ARPANET
- Projet ARPANET → relier universités et Défense (USA).
- 1983 : TCP/IP devient la pile officielle.

### FAI et Systèmes Autonomes
- **FAI (ISP)** : Fournisseur d’accès Internet.
- **AS (Autonomous System)** : ensemble de réseaux IP (ex : URCA reliée à un réseau local).

### Web ≠ Internet
- **Internet** = infrastructure réseau.  
- **Web** (1990) = pages accessibles via HTTP.  
- Autres services d’Internet :
- FTP (transfert de fichiers)
- Newsgroups (1979)
- Navigateur = télécharge et interprète des pages Web.

### Navigateur et HTTP
- Le navigateur envoie une requête HTTP au serveur.  
- Il récupère du **HTML** puis renvoie d’autres requêtes (images, scripts, CSS…).
- Le HTML est **interprété** et affiché.

---

## HTTP en détail

### Principe Client / Serveur
- **Client** établit une connexion et envoie une requête.
- **Serveur** traite et renvoie une réponse.

### Protocole sans état
- Le serveur ne garde pas la mémoire d’une requête précédente.
- TCP peut garder la connexion ouverte, mais le serveur n’en tient pas compte.

### Codes de statut HTTP
- `200 OK` : succès
- `301 Moved Permanently` : redirection
- `404 Not Found` : ressource absente

---

## Cookies
- Petit fichier stocké par le navigateur pour **maintenir un état**.  
- Exemples :
- Connexion utilisateur
- Préférences
- Créés via :
- Serveur → en-tête `Set-Cookie`
- Client → JavaScript (`document.cookie`)
- Exemple : connexion persistante sur un site.

---

## Serveurs Web et Hébergeurs
- Serveur HTTP = logiciel (Apache, Nginx…).
- Hébergeurs :
- AWS, Google Cloud, OVH, 1&1.
- Intérêt : disponibilité, gain de temps, sécurité.

---

## DNS et URL

### DNS
- **DNS (Domain Name System)** = traduit un nom en IP.  
- Fonctionnement :
- Requête envoyée à un serveur DNS.
- Résolution itérative (racine → TLD → domaine).
- Cache pour accélérer les recherches.

### URL
- **Uniform Resource Locator** : identifie une ressource.
- Format :
```

protocole://hôte:port/chemin/fichier

```
- Exemple :
```

[https://thor.univ-reims.fr:443/mesinfos/general.php](https://thor.univ-reims.fr:443/mesinfos/general.php)

````
- **URL absolue** : complète.  
- **URL relative** : dépend du contexte.

---

## HTML

### Structure d’un document
```html
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="utf-8">
<title>Exemple</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
<h1>Un titre</h1>
<p>Un paragraphe <strong>important</strong>.</p>
</body>
</html>
````

### Balises et attributs

* `<h1>` … `<h6>` : titres
* `<p>` : paragraphe
* `<a href="url">` : lien
* `<img src="image.png" alt="texte alternatif">`
* `<input type="checkbox" checked>` : attribut booléen

### Listes, liens, tableaux

* Liste non ordonnée :

  ```html
  <ul>
    <li>Un</li>
    <li>Deux</li>
  </ul>
  ```
* Liste ordonnée :

  ```html
  <ol>
    <li>Étape 1</li>
    <li>Étape 2</li>
  </ol>
  ```
* Tableau :

  ```html
  <table>
    <thead>
      <tr><th>Nom</th><th>Âge</th></tr>
    </thead>
    <tbody>
      <tr><td>Alice</td><td>22</td></tr>
    </tbody>
  </table>
  ```

### Multimédia et accessibilité

* Image :

  ```html
  <img src="chat.png" alt="Un chat mignon" width="300">
  ```
* Vidéo :

  ```html
  <video controls>
    <source src="video.mp4" type="video/mp4">
  </video>
  ```
* Texte alternatif obligatoire pour l’accessibilité.


---

# Partie HTML et CSS Cours Détaillé

## HTML : le langage de structure

### 1. Rôle du HTML
- Le **HTML (HyperText Markup Language)** décrit la structure d’une page web.
- Il ne s’occupe pas du style ni de la mise en page → uniquement de l’**organisation du contenu**.
- Une page HTML est composée d’**éléments** (ou balises) hiérarchisés.

---

### 2. Anatomie d’une balise
Une balise HTML a généralement :
- une **balise ouvrante** `<p>`
- un **contenu** `Bonjour`
- une **balise fermante** `</p>`

Exemple :
```html
<p>Bonjour</p>
````

Certaines balises sont **auto-fermantes** :

```html
<img src="photo.png" alt="ma photo">
```

---

### 3. Structure d’une page HTML

Une page suit une **structure standardisée** :

* `<!DOCTYPE html>` : annonce du type de document
* `<html>` : élément racine
* `<head>` : métadonnées (titre, encodage, CSS, scripts…)
* `<body>` : contenu affiché dans le navigateur

---

### 4. Catégories de balises

* **Texte** : `<h1>`, `<p>`, `<span>`, `<strong>`, `<em>`
* **Liens** : `<a href="...">`
* **Images et médias** : `<img>`, `<video>`, `<audio>`
* **Formulaires** : `<input>`, `<textarea>`, `<button>`
* **Structure** : `<header>`, `<nav>`, `<main>`, `<article>`, `<footer>`
* **Tableaux** : `<table>`, `<tr>`, `<td>`, `<th>`

---

### 5. Accessibilité

* Le HTML doit être compréhensible par **tous les utilisateurs** (y compris les malvoyants avec lecteurs d’écran).
* Règles :

  * Toujours mettre un attribut `alt` sur les images.
  * Utiliser des titres (`<h1>`, `<h2>`, …) dans le bon ordre.
  * Ne pas abuser des `<div>` si une balise sémantique existe.


### Formulaire HTML

### 1. Élément `<form>`

L’élément `<form>` permet de **regrouper des champs** pour envoyer des données à un serveur.

```html
<form action="traitement.php" method="post" target="_self">
  <!-- champs du formulaire ici -->
</form>
```

#### Attributs principaux :

| Attribut       | Description                                                                                      |
| -------------- | ------------------------------------------------------------------------------------------------ |
| `action`       | URL où les données seront envoyées lors de la validation du formulaire.                          |
| `method`       | Méthode d’envoi des données : `GET` (dans l’URL) ou `POST` (dans le corps de la requête).        |
| `target`       | Où afficher la réponse : `_self` (même fenêtre), `_blank` (nouvelle fenêtre), `_parent`, `_top`. |
| `id` / `class` | Identifiant ou classe CSS pour styliser le formulaire.                                           |
| `enctype`      | Type d’encodage des données (ex. `multipart/form-data` pour fichiers).                           |

*Remarque : `action` et `method` sont les plus utilisés, `target` est optionnel.*

---

### 2. Champs de formulaire courants

| Type de champ    | Exemple HTML                                           | Description                   |
| ---------------- | ------------------------------------------------------ | ----------------------------- |
| Texte            | `<input type="text" name="nom">`                       | Champ pour du texte simple    |
| Mot de passe     | `<input type="password" name="mdp">`                   | Texte masqué                  |
| Email            | `<input type="email" name="email">`                    | Vérifie le format email       |
| Nombre           | `<input type="number" name="age" min="0" max="100">`   | Champ numérique avec limites  |
| Case à cocher    | `<input type="checkbox" name="newsletter">`            | Choix multiple ou optionnel   |
| Bouton radio     | `<input type="radio" name="genre" value="H">Homme`     | Choix unique dans un groupe   |
| Zone de texte    | `<textarea name="message"></textarea>`                 | Texte sur plusieurs lignes    |
| Liste déroulante | `<select name="pays"><option>France</option></select>` | Choix parmi plusieurs options |
| Fichier          | `<input type="file" name="photo">`                     | Permet d’envoyer un fichier   |
| Bouton           | `<button type="submit">Envoyer</button>`               | Soumettre le formulaire       |

---

### 3. Exemple complet

```html
<form action="traitement.php" method="post" target="_self">
  <label for="nom">Nom :</label>
  <input type="text" id="nom" name="nom" required>

  <label for="email">Email :</label>
  <input type="email" id="email" name="email" required>

  <label for="genre">Genre :</label>
  <input type="radio" name="genre" value="H">Homme
  <input type="radio" name="genre" value="F">Femme

  <label for="newsletter">
    <input type="checkbox" name="newsletter"> Je souhaite recevoir la newsletter
  </label>

  <label for="message">Message :</label>
  <textarea name="message" id="message"></textarea>

  <button type="submit">Envoyer</button>
</form>
```

---

### 4. Points importants

* Chaque champ doit avoir un **attribut `name`**, sinon sa valeur ne sera pas envoyée.
* `method="post"` : données envoyées dans le **corps** de la requête (plus sécurisé).
* `method="get"` : données envoyées dans **l’URL** (pratique pour recherche, mais moins sécurisé).
* `required` : rend un champ **obligatoire**.
* `label` : améliore **l’accessibilité** et l’ergonomie.

```html
<form action="traitement.php" method="post">
  <label for="nom">Nom :</label>
  <input type="text" id="nom" name="nom" required autofocus placeholder="Ex : Dupont">

  <label for="email">Email :</label>
  <input type="email" id="email" name="email" required placeholder="exemple@domaine.com">

  <label for="code_postal">Code postal :</label>
  <input type="text" id="code_postal" name="code_postal" required pattern="[0-9]{5}" title="5 chiffres requis" placeholder="75000">

  <button type="submit">Envoyer</button>
</form>
```

**Résumé des attributs :**

* `required` → champ obligatoire.
* `autofocus` → place le curseur automatiquement.
* `pattern` → impose un format avec regex.
* `placeholder` → texte indicatif dans le champ.

---

---

## CSS : le langage de style

### 1. Rôle du CSS

* Le **CSS (Cascading Style Sheets)** gère la **présentation** d’une page HTML.
* Sépare le contenu (HTML) de l’apparence (CSS).
* Fonctionne par **règles** composées :

  * d’un **sélecteur** (élément ciblé)
  * d’un **bloc de déclarations** `{ propriété: valeur; }`

---

### 2. Le modèle de boîte (box model)

Chaque élément HTML est représenté comme une boîte rectangulaire :

1. **Content** : texte ou image de l’élément.
2. **Padding** : espace entre le contenu et la bordure.
3. **Border** : contour autour de l’élément.
4. **Margin** : espace entre l’élément et les autres.

Schéma simplifié :

```
+-------------------+
|     Margin        |
|  +-------------+  |
|  |   Border    |  |
|  | +---------+ |  |
|  | | Padding | |  |
|  | | Content | |  |
|  | +---------+ |  |
|  +-------------+  |
+-------------------+
```

---

### 3. Types d’affichage

* **Bloc (block)** : occupe toute la largeur, commence sur une nouvelle ligne.
  Ex : `<div>`, `<p>`, `<h1>`
* **En ligne (inline)** : occupe uniquement l’espace nécessaire, ne coupe pas la ligne.
  Ex : `<span>`, `<a>`, `<strong>`
* **Inline-block** : mélange des deux → reste en ligne mais accepte largeur/hauteur.

---

### 4. Flexbox (Flexible Box Layout)

Flexbox est un module CSS conçu pour simplifier :

* l’alignement
* la distribution de l’espace
* la création de mises en page dynamiques et adaptatives

#### Principes

* On définit un **conteneur flex** avec `display: flex;`
* Ses enfants deviennent des **éléments flexibles**.

#### Propriétés du conteneur

* `flex-direction` : direction principale (`row`, `column`, `row-reverse`, `column-reverse`)
* `justify-content` : alignement horizontal (`flex-start`, `center`, `space-between`, `space-around`)
* `align-items` : alignement vertical (`flex-start`, `center`, `stretch`, `baseline`)
* `flex-wrap` : retour à la ligne (`nowrap`, `wrap`)

#### Propriétés des enfants

* `flex-grow` : capacité à grandir
* `flex-shrink` : capacité à rétrécir
* `flex-basis` : taille de base avant ajustement

---

### 5. Responsive Design

Objectif : adapter la page à toutes les tailles d’écran.

Outils :

* **Media queries** : règles conditionnelles en fonction de la largeur de l’écran

```css
@media (max-width: 768px) {
  body {
    background-color: lightblue;
  }
}
```

* **Unités relatives** : `%`, `em`, `rem`, `vh`, `vw`
* **Images adaptatives** : `srcset` et attributs responsives

---


# Cours HTML & CSS – Niveau L1

## Table des matières

1. [HTML](#html)

   * [Structure d’un document](#structure-dun-document)
   * [Balises et attributs](#balises-et-attributs)
   * [Listes, liens et tableaux](#listes-liens-et-tableaux)
   * [Multimédia et accessibilité](#multimédia-et-accessibilité)
2. [CSS](#css)

   * [Fonctionnement des règles](#fonctionnement-des-règles)
   * [Sélecteurs](#sélecteurs)
   * [Modèle de boîte](#modèle-de-boîte)
   * [Flexbox](#flexbox)
   * [Responsive avec media queries](#responsive-avec-media-queries)

---

## HTML

### Structure d’un document

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <title>Exemple</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Mon titre</h1>
  <p>Un paragraphe <strong>important</strong>.</p>
</body>
</html>
```

* `<head>` → informations pour le navigateur (titre, CSS, scripts).
* `<body>` → contenu affiché.
* `<!DOCTYPE html>` → indique que le document est en HTML5.

### Balises et attributs

* Titres : `<h1>` à `<h6>`
* Paragraphe : `<p>`
* Lien : `<a href="url">texte</a>`
* Image : `<img src="image.png" alt="texte alternatif">`
* Formulaire : `<input type="text" name="nom">`

### Listes, liens et tableaux

**Liste non ordonnée :**

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

**Liste ordonnée :**

```html
<ol>
  <li>Étape 1</li>
  <li>Étape 2</li>
</ol>
```

**Tableau :**

```html
<table>
  <thead>
    <tr><th>Nom</th><th>Âge</th></tr>
  </thead>
  <tbody>
    <tr><td>Alice</td><td>22</td></tr>
    <tr><td>Bob</td><td>25</td></tr>
  </tbody>
</table>
```

### Multimédia et accessibilité

* Image : `<img src="chat.png" alt="Un chat mignon" width="300">`
* Vidéo :

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
</video>
```

* Toujours inclure `alt` pour accessibilité.

---

## CSS

### Fonctionnement des règles

* Une règle CSS = **sélecteur + déclaration**

```css
p {
  color: blue;
  font-size: 16px;
}
```

### Sélecteurs

* Par type : `p`
* Par classe : `.ma-classe`
* Par id : `#mon-id`
* Combinateurs :

  * Descendant : `li strong`
  * Enfant direct : `ul > li`
  * Frère adjacent : `h1 + p`
* Pseudo-classes : `a:hover`, `a:visited`
* Pseudo-éléments : `::first-letter`, `::selection`

---

### Modèle de boîte (Box Model)

Chaque élément HTML est une **boîte** composée de :

* **Content** → contenu
* **Padding** → marge intérieure
* **Border** → bordure
* **Margin** → marge extérieure

```css
div {
  width: 200px;
  padding: 10px;
  border: 5px solid black;
  margin: 20px;
}
```

Types de boîtes :

* **Bloc** : `div`, `p`, `h1` → occupe toute la largeur
* **Inline** : `span`, `a`, `em` → largeur du contenu

---

### Flexbox

Flexbox permet d’aligner facilement des éléments et de créer des mises en page **flexibles et adaptatives**.

**Conteneur Flex :**

```css
.container {
  display: flex;        /* active Flexbox */
  flex-direction: row;  /* direction des enfants (row / column) */
  flex-wrap: wrap;      /* permet le retour à la ligne si nécessaire */
  justify-content: space-between; /* alignement horizontal */
  align-items: center;  /* alignement vertical */
}
```

**Éléments Flex :**

```css
.item {
  flex: 1;             /* prend la même place */
  margin: 10px;        /* espace entre éléments */
}
```

**Principales propriétés Flexbox :**

* `flex-direction` : `row`, `column`, `row-reverse`, `column-reverse`
* `justify-content` : `flex-start`, `center`, `space-between`, `space-around`
* `align-items` : `flex-start`, `center`, `stretch`, `baseline`
* `flex-wrap` : `nowrap`, `wrap`, `wrap-reverse`
* `flex` sur les enfants : proportion de l’espace occupé

**Exemple HTML :**

```html
<div class="container">
  <div class="item">A</div>
  <div class="item">B</div>
  <div class="item">C</div>
</div>
```

---

### Responsive avec media queries

Les **media queries** permettent d’adapter le style à la taille de l’écran.

```css
/* Petit écran */
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
  p {
    font-size: 14px;
  }
}

/* Écran moyen et grand */
@media (min-width: 601px) {
  .container {
    flex-direction: row;
  }
  p {
    font-size: 16px;
  }
}
```

**Techniques complémentaires :**

* Utiliser des **unités relatives** : `em`, `rem`, `vw`, `vh`
* Images responsive avec `srcset` :

```html
<img srcset="chat_small.png 600w,
             chat_medium.png 800w,
             chat_large.png 1400w"
     src="chat_large.png" alt="chat mignon">
```

## les bibliothèque CSS et JS

il existe des bibliothèque (CSS, JavaScript), avant coder vérifiez si une bibliothèque ne fait pas déja le travail

### Comment choisir sa bibliotheque 

1. **Fonctionnalités** : Vérifie qu’elle fait ce dont tu as besoin sans alourdir ton projet.
2. **Popularité et communauté** : Une bibliothèque populaire est mieux documentée et maintenue.
3. **Maintenance et mises à jour** : Privilégie les bibliothèques régulièrement mises à jour.
4. **Performance** : Préfère les solutions légères pour ne pas ralentir le site.
5. **Compatibilité** : Assure-toi qu’elle fonctionne sur tous les navigateurs ciblés.
6. **Licence** : Vérifie que son utilisation est autorisée pour ton projet.
7. **Documentation** : Une bonne doc facilite l’apprentissage et l’intégration.

## Qu'est ce qu'un CDN (content delivery network)

utilisé génralemnt pour :
Voici une version complète et concise :

Un **CDN** est un réseau de serveurs distribués géographiquement qui permet de **livrer plus rapidement des contenus web** (fichiers CSS, JavaScript, images, vidéos, polices…).

### Utilisé généralement pour :

1. **Améliorer la vitesse de chargement** : les fichiers sont servis depuis le serveur le plus proche de l’utilisateur.
2. **Réduire la charge du serveur principal** : le trafic est réparti sur plusieurs serveurs.
3. **Assurer la disponibilité et la fiabilité** : en cas de panne d’un serveur, un autre prend le relais.
4. **Optimiser la diffusion de contenus statiques** : fichiers CSS, JS, images, vidéos, polices, etc.


## Bootstrap

**Bootstrap** est une **bibliothèque front-end** qui simplifie la création et le design de sites web modernes.

* Elle fournit du **HTML, CSS et JavaScript** prêts à l’emploi.
* Permet de créer des **interfaces responsives**, adaptées à tous les types d’écrans (ordinateurs, tablettes, mobiles).
* Contient de nombreux **composants préconçus** : boutons, formulaires, menus de navigation, carrousels, modals, alertes…
* Facilite la **mise en page** grâce à un **système de grille (Grid)** et à des **classes utilitaires** pour gérer marges, paddings, couleurs, typographie…
* Réduit le temps de développement et assure une **cohérence visuelle** sur l’ensemble du site.
* Compatible avec la plupart des navigateurs modernes et régulièrement mis à jour.


### Conteneur, ligne et colonne (Bootstrap)

Bootstrap utilise un **système de grille (Grid system)** basé sur **conteneurs, lignes et colonnes** pour organiser les éléments.

#### Structure de base :

```html
<div class="container">  <!-- Conteneur principal -->
  <div class="row">      <!-- Ligne -->
    <div class="col-2">  <!-- Première colonne -->
      Première colonne
    </div>
    <div class="col-8">  <!-- Deuxième colonne -->
      Deuxième colonne
    </div>
  </div>
</div>
```

#### Explications :

* **`container`** : centre le contenu et limite sa largeur selon la taille de l’écran.
* **`row`** : regroupe les colonnes et gère l’alignement horizontal.
* **`col-*`** : définit la largeur de chaque colonne (sur 12 parts par défaut).

#### Gestion du responsive :

* Les classes **`col-sm-*`, `col-md-*`, `col-lg-*`** permettent d’adapter la largeur des colonnes selon la taille de l’écran.
* Exemple :

```html
<div class="col-12 col-md-6">  
  Sera pleine largeur sur mobile, moitié largeur sur écran moyen et plus
</div>
```


### Classes pour gérer le responsive (Bootstrap)

Bootstrap permet de créer des mises en page **adaptatives** grâce à des classes spécifiques selon la **taille de l’écran**.

#### Tailles d’écran principales :

* **`xs`** : extra small (moins de 576px) → souvent utilisé par défaut (`col-*`)
* **`sm`** : small (≥ 576px)
* **`md`** : medium (≥ 768px)
* **`lg`** : large (≥ 992px)
* **`xl`** : extra large (≥ 1200px)
* **`xxl`** : extra extra large (≥ 1400px)

#### Exemple d’utilisation :

```html
<div class="container">
  <div class="row">
    <div class="col-12 col-md-6 col-lg-4">
      Colonne responsive
    </div>
    <div class="col-12 col-md-6 col-lg-8">
      Colonne responsive
    </div>
  </div>
</div>
```

* **`col-12`** → pleine largeur sur petits écrans
* **`col-md-6`** → moitié largeur sur écrans moyens
* **`col-lg-4` / `col-lg-8`** → proportion différente sur grands écrans

#### Autres classes utiles pour le responsive :

* **`d-`** : gestion de l’affichage (`d-none`, `d-sm-block`, `d-lg-flex`)
* **`order-`** : réorganisation des colonnes selon la taille (`order-md-2`)
* **`align-items-` / `justify-content-`** : alignement vertical et horizontal responsive



### Les couleurs (Bootstrap)

Bootstrap propose **des classes de couleurs par défaut** pour faciliter le style des éléments :

#### Couleurs principales :

* `primary` → bleu (valeur par défaut)
* `secondary` → gris
* `success` → vert
* `danger` → rouge
* `warning` → jaune/orange
* `info` → cyan
* `light` → clair
* `dark` → foncé

#### Utilisation :

Ces classes peuvent être utilisées pour :

* **Texte** : `text-success`
* **Arrière-plan** : `bg-success`
* **Boutons** : `btn btn-success`

#### Exemple avec une boîte :

```html
<div class="alert alert-success" role="alert">
  Succès ! Votre opération a été réalisée.
</div>
```

* `alert` → style de boîte d’alerte
* `alert-success` → couleur verte (succès)


### Marges et remplissage (Bootstrap) – version LTR/RTL compatible

La règle d’écriture des classes reste :

```
{type}-{direction}-{taille}
```

* **type** : `m` → margin, `p` → padding
* **direction** :

  * `t` → top (haut)
  * `b` → bottom (bas)
  * `s` → start (début, gauche en LTR)
  * `e` → end (fin, droite en LTR)
  * `x` → horizontal (start + end)
  * `y` → vertical (top + bottom)
  * rien → toutes les directions
* **taille** : `0` à `5`

#### Exemples :

```html
<div class="mt-3">Marge haute de 1rem</div>
<div class="ps-2">Padding au début (start) de 0.5rem</div>
<div class="me-4">Marge à la fin (end) de 1.5rem</div>
<div class="m-0 p-1">Marge 0 et padding 0.25rem sur toutes les directions</div>
```

* `ps-2` → padding sur le côté **start** (gauche en LTR, droite en RTL)
* `me-4` → margin sur le côté **end** (droite en LTR, gauche en RTL)

Cette notation est **préférable aux `l` et `r`** pour garantir la compatibilité avec les langues qui s’écrivent de droite à gauche.

# Cours serveur


## Programmation web “dynamique”

Contrairement à un site **statique** qui affiche toujours le même contenu, un site **dynamique** génère des pages **à la volée** en fonction des requêtes, des utilisateurs ou des données.

### 1. Interprétation côté serveur

* Le **serveur web** reçoit une requête HTTP du navigateur.
* Il exécute un **script ou code côté serveur** (PHP, Python, JavaScript avec Node.js, Java, Ruby, etc.).
* Ce code peut générer différents types de contenus en réponse :

  * **HTML** pour afficher une page web
  * **JSON** pour des échanges de données avec des applications ou AJAX
  * **Images**, fichiers PDF ou autres formats selon le besoin
* Cela permet de créer des sites interactifs, forums, boutiques en ligne, dashboards, etc.

### 2. Serveurs web et moteurs d’exécution

* Un **serveur web** est une application qui **écoute les requêtes HTTP** et y répond.
* Souvent, le serveur web est **couplé à un moteur d’exécution** pour le langage choisi, par exemple :

  * PHP → moteur PHP intégré
  * Python → via Flask, Django, ou WSGI
  * Node.js → serveur JavaScript natif
* Exemples de serveurs web courants :

  * **Apache**
  * **Nginx**
  * **IIS** (Windows)

### 3. Packs tout-en-un pour développement local

Pour tester et développer un site dynamique sur son ordinateur, on peut installer des **distributions complètes** qui regroupent serveur web + moteur + base de données :

* **Windows** : WAMP (Windows + Apache + MySQL + PHP), Laragon, EasyPHP, UwAmp
* **Mac** : MAMP (Mac + Apache + MySQL + PHP)
* **Linux** : LAMP (Linux + Apache + MySQL/MariaDB + PHP)

Ces environnements permettent de **simuler un serveur web localement**, sans avoir besoin de déployer le site sur Internet, ce qui est pratique pour le développement et les tests.



## Gestionnaire de base de données (SGBD)

Un **Système de Gestion de Base de Données (SGBD)** est un logiciel qui permet de **stocker, organiser et manipuler les données** utilisées par des applications web ou logicielles.

### À quoi ça sert ?

* Stocker les **données des utilisateurs** (nom, email, mot de passe, préférences…).
* Gérer les **données métier** d’une application (produits, commandes, articles, statistiques…).
* Assurer la **cohérence, sécurité et intégrité** des données.
* Permettre des **requêtes rapides et efficaces** pour récupérer ou modifier les données.

### Types de bases de données :

1. **Relationnelle**

   * Organise les données en **tables** avec des **lignes (enregistrements)** et des **colonnes (champs)**.
   * Les tables peuvent être liées entre elles par des **relations** (clé primaire / clé étrangère).
   * Langage principal : **SQL** (Structured Query Language).
   * Exemples : MySQL, PostgreSQL, MariaDB, Oracle.

2. **Non relationnelle (NoSQL)**

   * Utilisée pour des données plus flexibles ou volumineuses.
   * Peut stocker des documents, des paires clé/valeur, des graphes, etc.
   * Exemples : MongoDB, Redis, Cassandra.

### Schema de fonctionnement

Un schéma typique d’une application web dynamique avec base de données :

![Schéma client-serveur-base de données](https://s3-us-west-2.amazonaws.com/s.cdpn.io/363313/php_client_server_database.svg)

* Le **client (navigateur)** envoie une requête HTTP.
* Le **serveur web** exécute le code serveur (PHP, Python, etc.).
* Le code serveur interagit avec le **SGBD** pour lire ou modifier les données.
* Les données sont renvoyées au **client** sous forme de HTML, JSON ou autre.


