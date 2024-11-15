### **Documentation sur les CSS (Cascading Style Sheets)**

---

### **1. Qu'est-ce que les CSS ?**

CSS (Cascading Style Sheets) est un langage utilisé pour styliser les pages HTML. Il permet de définir l'apparence des éléments (couleurs, polices, marges, positions, etc.) et de séparer le contenu (HTML) de la présentation (CSS).

---

### **2. Structure d'une règle CSS**

Une règle CSS se compose de trois parties principales :

```css
sélecteur {
  propriété: valeur;
}
```

- **Sélecteur** : Désigne l’élément HTML à styliser (par exemple, un `h1`, un `p`, une `classe`).
- **Propriété** : Détermine l’aspect que vous voulez modifier (comme la couleur, la taille, etc.).
- **Valeur** : Spécifie le paramètre pour cette propriété.

**Exemple** :

```css
p {
  color: blue; /* La couleur du texte des paragraphes sera bleue */
  font-size: 16px; /* Taille de la police : 16 pixels */
}
```

---

### **3. Les différentes façons d'ajouter du CSS**

1. **CSS en ligne** (dans l'attribut `style` d'un élément HTML) :
   - À utiliser pour des modifications rapides.
   ```html
   <p style="color: blue; font-size: 16px;">Texte stylisé</p>
   ```

2. **CSS interne** (dans une balise `<style>` dans le fichier HTML) :
   - À utiliser pour des projets simples ou des tests.
   ```html
   <head>
     <style>
       p {
         color: blue;
       }
     </style>
   </head>
   ```

3. **CSS externe** (dans un fichier `.css` séparé) :
   - La meilleure pratique pour les projets complexes. Il suffit de lier le fichier dans le `<head>` de votre HTML.
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

---

### **4. Les types de sélecteurs**

1. **Sélecteur par balise** :
   - Cible tous les éléments d’un type donné.
   ```css
   h1 {
     color: red;
   }
   ```

2. **Sélecteur par classe** :
   - Cible des éléments ayant une classe spécifique (préfixée par un point `.`).
   ```css
   .highlight {
     background-color: yellow;
   }
   ```

   **HTML correspondant :**
   ```html
   <p class="highlight">Texte en surbrillance</p>
   ```

3. **Sélecteur par ID** :
   - Cible un élément avec un ID spécifique (préfixé par `#`).
   ```css
   #unique {
     font-weight: bold;
   }
   ```

   **HTML correspondant :**
   ```html
   <div id="unique">Texte unique</div>
   ```

4. **Sélecteurs combinés** :
   - Combine plusieurs sélecteurs pour cibler des éléments précis.
   ```css
   div p {
     color: green; /* Cible les paragraphes à l'intérieur des div */
   }
   ```

5. **Pseudo-classes** :
   - Ciblent un état particulier d'un élément.
   ```css
   a:hover {
     color: orange; /* Change la couleur d'un lien lorsqu'il est survolé */
   }
   ```

---

### **5. Propriétés CSS essentielles**

1. **Couleurs et arrière-plans** :
   ```css
   color: red; /* Couleur du texte */
   background-color: lightblue; /* Couleur de l'arrière-plan */
   ```

2. **Police et texte** :
   ```css
   font-family: Arial, sans-serif; /* Police du texte */
   font-size: 18px; /* Taille du texte */
   text-align: center; /* Alignement du texte */
   ```

3. **Marges et espacements** :
   ```css
   margin: 10px; /* Espace extérieur */
   padding: 15px; /* Espace intérieur */
   ```

4. **Bordures** :
   ```css
   border: 2px solid black; /* Bordure pleine noire */
   border-radius: 10px; /* Coins arrondis */
   ```

5. **Taille et positionnement** :
   ```css
   width: 50%; /* Largeur : 50% du parent */
   height: 100px; /* Hauteur : 100 pixels */
   position: absolute; /* Position absolue */
   ```

---

### **6. Le modèle de boîte (box model)**

Chaque élément HTML est considéré comme une boîte composée de :

- **Content** : Contenu de l’élément.
- **Padding** : Espace intérieur autour du contenu.
- **Border** : Bordure autour du padding.
- **Margin** : Espace extérieur autour de l’élément.

**Exemple de styles liés au box model** :

```css
div {
  margin: 20px; /* Espace extérieur */
  padding: 10px; /* Espace intérieur */
  border: 2px solid black; /* Bordure */
}
```

---

### **7. Flexbox et Grid : mise en page moderne**

1. **Flexbox** : Pour aligner et répartir les éléments dans une direction (ligne ou colonne).
   ```css
   .container {
     display: flex;
     justify-content: center; /* Centrage horizontal */
     align-items: center; /* Centrage vertical */
   }
   ```

2. **Grid** : Pour créer des mises en page en grille.
   ```css
   .grid {
     display: grid;
     grid-template-columns: 1fr 2fr; /* Deux colonnes */
     grid-gap: 10px; /* Espacement entre les éléments */
   }
   ```

---

### **8. Média queries : CSS adaptatif**

Permet d'adapter le design en fonction de la taille de l'écran.

```css
@media (max-width: 600px) {
  body {
    font-size: 14px; /* Police plus petite pour les petits écrans */
  }
}
```

---

### **9. Bonnes pratiques CSS**

- **Organisez vos styles** : Groupez les règles logiquement.
- **Évitez le CSS en ligne** : Utilisez des fichiers externes pour une meilleure maintenance.
- **Réutilisez les classes** : Pour éviter les styles redondants.
- **Validez votre CSS** : Utilisez des outils comme [W3C CSS Validator](https://jigsaw.w3.org/css-validator/).

---

### **10. Exemple complet : Mise en page simple avec CSS**

**HTML :**
```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
  <title>Page Exemple</title>
</head>
<body>
  <header class="main-header">Bienvenue sur mon site</header>
  <main>
    <section class="content">
      <p class="highlight">Ceci est un texte important.</p>
    </section>
  </main>
  <footer class="main-footer">&copy; 2024 Mon Site</footer>
</body>
</html>
```

**CSS (styles.css) :**
```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}

.main-header, .main-footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px 0;
}

.content {
  padding: 20px;
  background-color: white;
  margin: 20px auto;
  max-width: 800px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

.highlight {
  color: red;
  font-weight: bold;
}
```

---

