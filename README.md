# Monster Hunter Ultimate Quiz

Une application web interactive et desktop pour tester vos connaissances sur l'univers de Monster Hunter !

## 📌 Fonctionnalités

✅ **200 questions vérifiées** (FR/EN) avec sources officielles Capcom
✅ **Système de quiz** avec timer, score, combo et statistiques
✅ **Design moderne** (React + TypeScript + Vite + TailwindCSS)
✅ **Animations fluides** et effets sonores immersifs
✅ **Responsive** (PC, tablette, téléphone)
✅ **Accessibilité** (navigation clavier, focus visible, contraste)
✅ **Bilingue** (Français / Anglais)
✅ **Version desktop** (.exe généré via Electron)
✅ **Système de succès** et récompenses
✅ **Révisions des réponses** avec explications et sources

---

## 🚀 Installation et Lancement

### 1️⃣ Prérequis
- [Node.js (v18 ou supérieur)](https://nodejs.org/fr/download/)
- Un navigateur moderne (Chrome, Firefox, Edge)

### 2️⃣ Installation

#### **Version Web (développement)**
```bash
# Clonez le dépôt
git clone https://github.com/wyverndescaverne-ship-it/mh-ultimate-quiz-app.git
cd mh-ultimate-quiz-app

# Installez les dépendances
npm install

# Lancez l'application en mode développement
npm run dev
```

L'application sera accessible à l'adresse : [http://localhost:5173](http://localhost:5173)

---

#### **Version Desktop (.exe)**
```bash
# Installez les dépendances (si ce n'est pas déjà fait)
npm install

# Générez le build de production
npm run build

# Générez l'exécutable (.exe)
npm run package
```

L'exécutable sera disponible dans le dossier :
```
dist/win-unpacked/MonsterHunterUltimateQuiz.exe
```

---

## 📂 Structure du Projet

```
src/
├── components/       # Composants React réutilisables
├── pages/            # Pages principales (Quiz, Menu, Fin, etc.)
├── data/             # Fichiers de données (questions, catégories, etc.)
├── hooks/            # Hooks personnalisés
├── services/         # Services (API, audio, etc.)
├── utils/            # Utilitaires (traductions, validations, etc.)
├── types/            # Types TypeScript
├── i18n/             # Traductions (FR/EN)
├── styles/           # Styles globaux et TailwindCSS
├── audio/            # Fichiers audio (musiques, effets sonores)
└── images/           # Images (logos, fonds, etc.)

public/
├── audio/            # Fichiers audio pour le quiz
└── images/           # Images pour l'interface

scripts/
└── validateQuestions.ts  # Script de validation des questions

.vite/              # Configuration Vite
.eslintrc.cjs       # Configuration ESLint
.prettierrc         # Configuration Prettier
index.html          # Point d'entrée HTML
package.json        # Dépendances et scripts
vite.config.ts      # Configuration Vite
```

---

## 📖 Guide d'Utilisation

### 🎮 Jouer au Quiz
1. Lancez l'application en mode web (`npm run dev`) ou ouvrez l'exécutable `.exe`.
2. Sélectionnez une langue (FR/EN).
3. Choisissez une catégorie ou commencez le quiz général.
4. Répondez aux questions dans le temps imparti (5 secondes par question).
5. À la fin, consultez votre score, vos statistiques et révisez les réponses.

### 🔍 Réviser les Réponses
Après le quiz, vous pouvez consulter :
- La question
- Votre réponse
- La bonne réponse
- Une explication détaillée
- La source officielle (lien Capcom)

### ⚙️ Personnalisation
Vous pouvez ajouter ou modifier des questions en éditant le fichier :
```
src/data/questions.json
```

---

## 🛠️ Configuration et Personnalisation

### Ajouter une Question
1. Éditez le fichier `src/data/questions.json`.
2. Ajoutez un nouvel objet dans le tableau `questions` avec la structure suivante :
   ```json
   {
     "id": 201,
     "game": "Monster Hunter Wilds",
     "category": "Monstres",
     "difficulty": "Difficile",
     "question": {
       "fr": "Quel monstre est introduit dans Monster Hunter Wilds ?",
       "en": "Which monster is introduced in Monster Hunter Wilds?"
     },
     "answers": [
       {
         "text": {"fr": "Nargacuga", "en": "Nargacuga"},
         "isCorrect": false
       },
       {
         "text": {"fr": "Evolved Gargwa", "en": "Evolved Gargwa"},
         "isCorrect": false
       },
       {
         "text": {"fr": "Ironshell", "en": "Ironshell"},
         "isCorrect": true
       }
     ],
     "correctAnswer": 2,
     "explanation": {
       "fr": "Ironshell est un nouveau monstre introduit dans Monster Hunter Wilds, connu pour sa carapace résistante.",
       "en": "Ironshell is a new monster introduced in Monster Hunter Wilds, known for its tough shell."
     },
     "source": {
       "url": "https://www.monsterhunter.com/wilds/",
       "text": {"fr": "Site officiel Monster Hunter Wilds", "en": "Official Monster Hunter Wilds Website"}
     }
   }
   ```
3. Validez le format avec la commande :
   ```bash
   npx tsx scripts/validateQuestions.ts
   ```

### Changer la Langue
1. Ajoutez ou modifiez les fichiers dans `src/i18n/`.
2. Les traductions sont automatiquement chargées en fonction de la langue sélectionnée.

### Modifier le Design
1. Éditez les fichiers dans `src/styles/` pour les styles globaux.
2. Modifiez les composants dans `src/components/` pour personnaliser l'interface.

---

## 🎵 Audio et Animations

### Ajouter un Son
1. Placez votre fichier audio dans `public/audio/`.
2. Utilisez le service `audioService.ts` pour charger et jouer le son.

### Ajouter une Animation
1. Utilisez des classes TailwindCSS ou des animations CSS personnalisées dans `src/styles/`.
2. Pour des animations complexes, utilisez des bibliothèques comme Framer Motion.

---

## 📊 Statistiques et Succès

### Système de Score
- **Score total** : Points accumulés pendant le quiz.
- **Pourcentage** : Ratio de bonnes réponses.
- **Combo max** : Meilleure série de bonnes réponses consécutives.
- **Temps moyen** : Temps moyen pour répondre aux questions.

### Succès
Les succès sont définis dans `src/data/achievements.json`. Vous pouvez en ajouter ou modifier les conditions.

---

## 🔧 Scripts Disponibles

| Script | Description |
|--------|-------------|
| `npm run dev` | Lance l'application en mode développement |
| `npm run build` | Génère une version optimisée pour la production |
| `npm run preview` | Prévise la version de production |
| `npm run package` | Génère l'exécutable (.exe) pour Windows |
| `npm run lint` | Vérifie la qualité du code avec ESLint |
| `npm run format` | Formate le code avec Prettier |
| `npx tsx scripts/validateQuestions.ts` | Valide la structure des questions |

---

## 📜 Licence

Ce projet est sous licence **MIT**. Vous êtes libre de l'utiliser, le modifier et le redistribuer.

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Ouvrez une **issue** ou soumettez une **pull request** pour améliorer le projet.

---

## 📬 Contact

Pour toute question ou suggestion, contactez-moi sur GitHub : [wyverndescaverne-ship-it](https://github.com/wyverndescaverne-ship-it).

---

## 📸 Captures d'Écran

*(À venir : images de l'interface du quiz, écran de fin, menu, etc.)*