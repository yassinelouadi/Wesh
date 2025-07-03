# Wesh Dating App - Application de Rencontres Style Tinder

## Vue d'ensemble
Wesh est une application de rencontres moderne inspirée de Tinder, avec des fonctionnalités de swipe, matching, et messagerie. L'application inclut un logo cœur animé qui tourne à 360° et une interface utilisateur fluide.

## Fonctionnalités implémentées

### ✅ Interface utilisateur type Tinder
- **Système de swipe** : Glissez à droite pour liker, à gauche pour passer
- **Cartes de profils** : Photos avec informations (nom, âge, bio, distance)
- **Boutons d'action** : Rejeter, Super Like, et Like
- **Navigation mobile** : Interface responsive optimisée mobile

### ✅ Logo animé unique
- **Rotation 360°** : Logo cœur qui tourne en continu
- **Effets visuels** : Pulsation et glow effects
- **Animation de chargement** : Écran de démarrage avec logo animé

### ✅ Système de matching
- **Algorithme de match** : Simulation de correspondances (20% de chance)
- **Modal de match** : Animation célébrant les nouveaux matches
- **Gestion des profils** : API pour charger et gérer les profils

### ✅ Section Messages
- **Liste des matches** : Aperçu des conversations
- **Statut de lecture** : Indicateurs de messages non lus
- **Navigation fluide** : Transition entre découverte et messages

## Configuration pour Windows avec VS Code

### Prérequis
1. **Node.js** version 18 ou supérieure
2. **VS Code** avec les extensions suivantes :
   - TypeScript and JavaScript Language Features
   - ES7+ React/Redux/React-Native snippets
   - Tailwind CSS IntelliSense
   - Auto Rename Tag

### Installation rapide

```bash
# Cloner le projet
git clone [votre-repo]
cd wesh-dating-app

# Installer les dépendances
npm install

# Démarrer le serveur de développement
npm run dev
```

### Scripts disponibles

```bash
# Développement
npm run dev          # Démarre le serveur avec hot-reload

# Production
npm run build        # Compile pour la production
npm start           # Démarre le serveur de production

# Vérification
npm run check       # Vérification TypeScript
```

### Structure du projet
```
wesh-dating-app/
├── client/          # Frontend React
│   ├── src/
│   │   ├── App.tsx  # Application principale
│   │   ├── main.tsx # Point d'entrée
│   │   └── index.css # Styles
│   └── index.html
├── server/          # Backend Express
│   └── index.ts     # Serveur principal
├── shared/          # Types partagés
│   └── schema.ts    # Interfaces TypeScript
└── package.json
```

### Configuration VS Code recommandée

Créez `.vscode/settings.json` :
```json
{
  "typescript.preferences.importModuleSpecifier": "relative",
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  },
  "editor.formatOnSave": true,
  "files.exclude": {
    "**/node_modules": true,
    "**/dist": true
  }
}
```

### Variables d'environnement (optionnel)
Créez un fichier `.env` :
```
PORT=5000
NODE_ENV=development
```

### Dépannage Windows

**Port occupé :**
```bash
netstat -ano | findstr :5000
taskkill /PID [PID] /F
```

**Problème de permissions :**
```bash
# Exécuter VS Code en tant qu'administrateur si nécessaire
```

### Prochaines étapes
1. Configurer la base de données PostgreSQL (optionnel pour le développement)
2. Ajouter l'authentification
3. Implémenter les fonctionnalités de matching
4. Configurer PayPal pour les paiements

Le projet est maintenant prêt pour le développement local sur Windows !