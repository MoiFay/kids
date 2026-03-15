# 🎮 Site de Mini-Jeux Éducatifs — 3 à 5 ans

Site statique 100% HTML/CSS/JS, prêt à déployer sur **GitHub Pages**.

---

## 📁 Structure du projet

```
site-jeux/
├── index.html          ← Page d'accueil (menu des jeux)
├── style.css           ← Feuille de style commune (mobile-first)
├── jeu-ballons.html    ← Jeu 1 : Ballons à éclater
├── jeu-couleurs.html   ← Jeu 2 : Trouver la bonne couleur
├── jeu-animaux.html    ← Jeu 3 : Cliquer sur le bon animal
├── jeu-fruits.html     ← Jeu 4 : Attraper les fruits
├── jeu-nombres.html    ← Jeu 5 : Compter les objets
├── jeu-anglais.html    ← Jeu 6 : Apprendre l'anglais
└── README.md
```

---

## 🚀 Déploiement sur GitHub Pages

### Méthode simple (recommandée)

1. Crée un dépôt GitHub (ex : `jeux-enfants`)
2. Charge tous les fichiers du dossier `site-jeux/` à la racine du dépôt
3. Va dans **Settings → Pages**
4. Source : **Deploy from a branch** → branche `main` → dossier `/root`
5. Clique **Save** — ton site sera accessible en quelques minutes sur :
   `https://TON_NOM.github.io/jeux-enfants/`

### Via Git en ligne de commande

```bash
git init
git add .
git commit -m "🎮 Site de jeux éducatifs"
git branch -M main
git remote add origin https://github.com/TON_NOM/jeux-enfants.git
git push -u origin main
```

---

## 🎮 Description des jeux

| Fichier | Jeu | Description |
|---------|-----|-------------|
| `jeu-ballons.html` | 🎈 Ballons | Des ballons montent, l'enfant les éclate en cliquant. Score + record. Accélération progressive. |
| `jeu-couleurs.html` | 🎨 Couleurs | Un nom de couleur s'affiche, l'enfant doit cliquer le bon rectangle. |
| `jeu-animaux.html` | 🐶 Animaux | Un nom d'animal s'affiche, l'enfant choisit le bon parmi 4. |
| `jeu-fruits.html` | 🍎 Fruits | Des fruits tombent, un fruit cible est demandé, timer 30 secondes. |
| `jeu-nombres.html` | 🔢 Compter | Des emojis s'affichent, l'enfant compte et choisit le bon chiffre (1-9). Chaque objet est cliquable pour compter interactivement. |
| `jeu-anglais.html` | 🇬🇧 English | 5 thèmes (chiffres, couleurs, jours, salutations, se présenter). Prononciation via SpeechSynthesis API. Sons de succès/erreur. |

---

## 📱 Compatibilité

- ✅ Mobile (iOS Safari, Chrome Android)
- ✅ Tablette (iPad, Android)
- ✅ Desktop
- ✅ Écrans tactiles (touch events)
- ✅ Pas de connexion requise après chargement initial (sauf police Google Fonts)

### Pour une utilisation hors-ligne complète

Remplace la ligne d'import Google Fonts dans `style.css` :

```css
/* Enlever cette ligne */
@import url('https://fonts.googleapis.com/css2?family=Fredoka+One&family=Nunito:wght@400;700;900&display=swap');
```

Et ajouter en fallback dans la déclaration `font-family` :
```css
font-family: 'Fredoka One', 'Comic Sans MS', cursive;
```

---

## 🔊 Synthèse vocale (jeu Anglais)

Le jeu d'anglais utilise l'**API Web SpeechSynthesis** (intégrée aux navigateurs modernes).

- Fonctionne sur Chrome, Edge, Safari (iOS/macOS), Firefox
- La voix anglaise est détectée automatiquement (en-GB préféré, sinon en-US)
- Si indisponible, le jeu fonctionne quand même sans son

---

## 🎨 Personnalisation

### Modifier les couleurs principales
Édite les variables CSS dans `style.css` :
```css
:root {
  --col-red:    #FF4B4B;
  --col-green:  #4CAF50;
  /* ... */
}
```

### Ajouter des animaux / fruits / mots
Modifie les tableaux JavaScript dans chaque fichier :
```js
// Exemple dans jeu-animaux.html
const ANIMALS = [
  { name: 'Chien', emoji: '🐶', sound: 'Ouaf !' },
  // Ajouter ici...
];
```

---

## 👶 Conseils d'utilisation

- Jouer en mode **plein écran** sur tablette pour une meilleure expérience
- Sur iPad : ajouter à l'écran d'accueil via Safari → "Ajouter à l'écran d'accueil"
- Les boutons sont volontairement très grands pour les petits doigts
- Le record du jeu Ballons est sauvegardé dans le navigateur (localStorage)
