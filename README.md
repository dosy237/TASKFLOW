
#  TaskFlow — Application de Gestion de Tâches

**Auteur :** DONFACK SYNTHIA CALORINE  
**Technologie :** React 18 + TypeScript + Tailwind CSS

---

##  Description

TaskFlow est une application web moderne de gestion de tâches permettant aux utilisateurs de créer, organiser et suivre leurs tâches quotidiennes. L'application offre une interface intuitive, rapide et sécurisée avec authentification, filtrage avancé et notifications en temps réel.

---

##  Fonctionnalités

###  Authentification
- Inscription avec nom, email et mot de passe
- Connexion avec vérification des identifiants
- Stockage sécurisé des utilisateurs en localStorage
- Affichage/masquage du mot de passe lors de la saisie
- Redirection automatique si non authentifié
- Messages d'erreur en français

###  Gestion des Tâches
- Afficher la liste de toutes les tâches
- Créer une nouvelle tâche (titre, catégorie, priorité, date limite)
- Supprimer une tâche
- Marquer une tâche comme terminée (avec animation)
- Animation confetti quand toutes les tâches sont terminées 🎉

###  Filtres et Organisation
- Filtrer par statut : Toutes, Actives, Terminées
- Filtrer par catégorie : Travail, Personnel, Urgent, Autre
- Filtrer par priorité : Haute , Moyenne , Basse 
- Navigation par sidebar avec catégories colorées

###  Notifications
- Panneau de notifications fonctionnel
- Rappels automatiques basés sur les tâches :
  -  Tâches en retard
  -  Tâches dues aujourd'hui
  -  Tâches dues demain
  -  Tâches haute priorité
- Badge de compteur sur l'icône cloche

###  Interface Utilisateur
- Design responsive (mobile, tablette, desktop)
- 10+ composants réutilisables
- Feedback visuel (loading, erreurs, succès)
- Animations fluides avec Framer Motion
- Thème vibrant et coloré

---

##  Installation

### Prérequis
- Node.js 18+
- npm ou yarn

### Étapes

```bash
# 1. Cloner le repository
git clone https://github.com/votre-repo/taskflow.git
cd taskflow

# 2. Installer les dépendances
npm install

# 3. Lancer le serveur de développement
npm run dev

# 4. Ouvrir dans le navigateur
# http://localhost:3000
```

---

##  Structure du Projet

```
taskflow/
├── index.tsx                    # Point d'entrée
├── index.css                    # Styles globaux + Tailwind
├── App.tsx                      # Composant racine + routage auth
├── tailwind.config.js           # Configuration Tailwind
│
├── types/
│   └── index.ts                 # Types TypeScript (Task, User, Category)
│
├── lib/
│   ├── utils.ts                 # Utilitaires (cn, getRelativeTime)
│   └── auth.ts                  # Service d'authentification
│
├── hooks/
│   └── useTasks.ts              # Hook personnalisé pour la gestion des tâches
│
├── components/
│   ├── ui/                      # Composants UI réutilisables
│   │   ├── Button.tsx           # Bouton avec variantes
│   │   ├── Input.tsx            # Champ de saisie avec toggle mot de passe
│   │   ├── Checkbox.tsx         # Case à cocher animée
│   │   └── Modal.tsx            # Modal avec animation
│   │
│   ├── Header.tsx               # En-tête avec recherche et notifications
│   ├── Sidebar.tsx              # Barre latérale avec navigation
│   ├── TaskCard.tsx             # Carte de tâche
│   ├── CreateTaskModal.tsx      # Modal de création de tâche
│   ├── CategoryPill.tsx         # Pastille de catégorie
│   ├── PriorityStars.tsx        # Étoiles de priorité
│   ├── ProgressRing.tsx         # Anneau de progression
│   └── EmptyState.tsx           # État vide
│
├── pages/
│   ├── AuthPage.tsx             # Page d'authentification
│   └── Dashboard.tsx            # Tableau de bord principal
│
└── docs/
    ├── README.md                # Ce fichier
    └── API.md                   # Documentation API
```

---

##  Composants Réutilisables (8+)

| Composant | Description | Props principales |
|-----------|-------------|-------------------|
| `Button` | Bouton avec 4 variantes | `variant`, `size`, `disabled` |
| `Input` | Champ avec label, erreur, toggle mdp | `label`, `error`, `type` |
| `Checkbox` | Case à cocher animée par catégorie | `checked`, `onChange`, `category` |
| `Modal` | Modal avec backdrop et animation | `isOpen`, `onClose`, `title` |
| `TaskCard` | Carte de tâche complète | `task`, `onToggle`, `onDelete` |
| `CategoryPill` | Pastille colorée de catégorie | `category`, `selected`, `onClick` |
| `PriorityStars` | Sélecteur de priorité 1-3 étoiles | `priority`, `onChange`, `readOnly` |
| `ProgressRing` | Anneau SVG de progression | `percentage`, `size`, `strokeWidth` |
| `EmptyState` | Message quand aucune tâche | — |
| `Header` | En-tête avec recherche + notifications | `user`, `tasks` |
| `Sidebar` | Navigation latérale | `selectedCategory`, `onLogout` |

---

##  Stockage des Données

L'application utilise `localStorage` pour persister les données :

| Clé | Contenu |
|-----|---------|
| `taskflow_users` | Liste des utilisateurs inscrits `[{name, email, password}]` |
| `taskflow_tasks` | Liste des tâches `[{id, title, category, ...}]` |

---

##  Sécurité

- Validation des champs côté client
- Vérification de l'existence de l'utilisateur à la connexion
- Vérification du mot de passe (minimum 6 caractères)
- Messages d'erreur explicites sans révéler d'informations sensibles

> **Note :** Dans un environnement de production, les mots de passe seraient hashés avec bcrypt et stockés dans une base de données sécurisée avec JWT pour l'authentification.

---

##  Technologies Utilisées

- **React 18** — Bibliothèque UI avec Hooks
- **TypeScript** — Typage statique
- **Tailwind CSS** — Framework CSS utilitaire
- **Framer Motion** — Animations fluides
- **Lucide React** — Icônes SVG
- **canvas-confetti** — Effet confetti de célébration

---

##  Utilisation

1. **Inscription** : Créez un compte avec votre nom, email et mot de passe
2. **Connexion** : Connectez-vous avec vos identifiants
3. **Créer une tâche** : Cliquez sur "Nouvelle Tâche" et remplissez le formulaire
4. **Organiser** : Utilisez la sidebar pour filtrer par catégorie
5. **Compléter** : Cochez les tâches terminées
6. **Notifications** : Cliquez sur la cloche pour voir les rappels

---

##  Auteur

**DONFACK SYNTHIA CALORINE**

---

##  Licence

Ce projet est réalisé dans le cadre d'un exercice académique.
