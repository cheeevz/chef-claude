# 👨‍🍳 Chef Claude

> Application React qui génère une recette à partir des ingrédients que vous avez sous la main, grâce à l'API Claude d'Anthropic.

---

## ✨ Fonctionnalités

- Ajout d'ingrédients via un formulaire simple
- Affichage dynamique de la liste des ingrédients
- Bouton « Obtenir une recette » qui apparaît dès qu'il y a assez d'ingrédients
- Génération d'une recette détaillée par l'IA (Claude)
- Rendu de la recette en Markdown (titres, listes, étapes)
- Interface responsive

## 🛠️ Stack technique

| Catégorie | Technologies |
|-----------|--------------|
| Front-end | React, JavaScript (ES6+), CSS |
| Build | Vite |
| IA | API Anthropic (Claude) |
| Rendu | react-markdown |

## 🧠 Ce que ce projet m'a permis de pratiquer

- Gestion d'état avec `useState`
- Formulaires et récupération des données avec `FormData`
- Rendu conditionnel et listes (`map`, `key`)
- Découpage en composants réutilisables et passage de props
- Appels API asynchrones (`async` / `await`) et gestion des erreurs
- Sécurisation d'une clé API (variables d'environnement, appel côté serveur)

## 📁 Structure du projet

```
chef-claude/
├── public/
│   ├── favicon.svg
│   └── icons.svg
├── src/
│   ├── assets/
│   │   └── images/
│   │       └── chef-claude-icon.png
│   ├── components/
│   │   ├── ClaudeRecipe.jsx   # Affichage de la recette générée
│   │   ├── Header.jsx         # En-tête de l'application
│   │   ├── Main.jsx           # Formulaire et liste des ingrédients
│   │   └── ai.js              # Appel à l'API Claude
│   ├── App.jsx
│   ├── index.css
│   └── index.jsx              # Point d'entrée
├── .env.example
├── .gitignore
├── .oxlintrc.json
├── index.html
├── package.json
└── vite.config.js
```

## 🚀 Installation et lancement

### Prérequis

- [Node.js](https://nodejs.org/) 18 ou plus
- Une clé API Anthropic ([console.anthropic.com](https://console.anthropic.com/))

### Étapes

```bash
# 1. Cloner le dépôt
git clone https://github.com/cheeevz/chef-claude.git
cd chef-claude

# 2. Installer les dépendances
npm install

# 3. Configurer la clé API
cp .env.example .env
# puis renseigner ta clé dans le fichier .env

# 4. Lancer le serveur de développement
npm run dev
```

L'application est ensuite accessible sur [http://localhost:5173](http://localhost:5173).

### Variables d'environnement

```env
VITE_ANTHROPIC_API_KEY=ta_cle_api_ici
```

> ⚠️ **Sécurité** : la clé API ne doit jamais être exposée dans le code front-end ni commitée sur GitHub. Le fichier `.env` est listé dans le `.gitignore`. En production, l'appel à l'API passe par une fonction serverless qui garde la clé côté serveur.

## 🌐 Déploiement

Le projet peut être déployé sur **Netlify** ou **Vercel** :

1. Connecter le dépôt GitHub à la plateforme
2. Commande de build : `npm run build` — dossier de sortie : `dist`
3. Ajouter `ANTHROPIC_API_KEY` dans les variables d'environnement du projet
4. Placer l'appel à l'API dans une fonction serverless (`netlify/functions/` ou `api/`)

## 🔮 Améliorations envisagées

- [ ] Suppression d'un ingrédient de la liste
- [ ] Sauvegarde des recettes favorites (localStorage)
- [ ] Indicateur de chargement pendant la génération
- [ ] Choix des contraintes : végétarien, temps de préparation, nombre de personnes
- [ ] Tests unitaires et end-to-end (Vitest, Cypress)

## 📚 Crédits

Projet réalisé dans le cadre du cours React de [Scrimba](https://scrimba.com/), puis enrichi personnellement.

## 👤 Auteur

**Clément Martin**
- GitHub : [@cheeevz](https://github.com/cheeevz)
- LinkedIn : [Clément Martin](https://www.linkedin.com/in/clement-martin-3487606b)

