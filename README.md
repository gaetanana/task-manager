# 📋 Task Manager

## 📌 À propos du projet

**Task Manager** est une application web complète de gestion de projets et de tâches. Elle permet de :
- ✅ Créer et gérer des projets
- 👥 Attribuer des tâches à des utilisateurs
- 📊 Suivre la progression des tâches via des statuts
- 🚀 Évoluer avec de nouvelles fonctionnalités

---

## 📋 Table des matières

1. [Prérequis](#prérequis)
2. [Installation](#installation)
3. [Scripts disponibles](#scripts-disponibles)
4. [Architecture du projet](#architecture-du-projet)
5. [Technologies utilisées](#technologies-utilisées)

---

## 📦 Prérequis

- **Node.js** (version 16+)
- **npm** ou **yarn**
- **PostgreSQL** (local ou via Docker)
- **Docker** et **Docker Compose** (optionnel)

---

## 🔧 Installation

### Étape 1 : Cloner le projet
```bash
git clone <repository-url>
cd task-manager
```

### Étape 2 : Installer les dépendances
```bash
npm install
```

### Étape 3 : Configurer la base de données

#### Avec Docker Compose
```bash
docker-compose up -d
```

La base de données PostgreSQL sera disponible à `localhost:5434` avec :
- **User** : postgres
- **Password** : postgres
- **Database** : task_manager


### Étape 4 : Migrer la base de données
```bash
npm run db:generate
npm run db:push
```

Faire attention au proxy si vous en avez un 

### Étape 5 : Démarrer l'application
```bash
npm start
```

L'application sera disponible à :
- **Frontend** : http://localhost:4000
- **Backend** : http://localhost:3000

---

## 🚀 Scripts disponibles

### À la racine du projet
```bash
npm start         # Démarre le frontend et backend simultanément
npm run build     # Construit le frontend et backend
```

### Frontend (`web-task-manager`)
```bash
npm run dev       # Démarre le serveur de développement
npm run build     # Construit pour la production
npm run lint      # Exécute ESLint
```

### Backend (`back-task-manager`)
```bash
npm start         # Démarre le serveur
npm run dev       # Mode de développement avec hot-reload
npm run build     # Construit l'application
npm run lint      # Exécute ESLint
```

---

## 📁 Architecture du projet

```
task-manager/
├── back-task-manager/      # Application NestJS (Backend)
│   ├── src/
│   ├── package.json
│   └── tsconfig.json
├── web-task-manager/       # Application Next.js (Frontend)
│   ├── app/
│   ├── public/
│   ├── package.json
│   └── tsconfig.json
├── prisma/                 # Configuration ORM Prisma
│   ├── schema.prisma
│   └── .env
├── docker-compose.yml      # Configuration Docker
└── package.json            # Configuration racine
```

---

## 🛠️ Technologies utilisées

| Couche | Technologie | Usage |
|--------|-------------|-------|
| **Frontend** | [Next.js](https://nextjs.org/) | Framework React moderne |
| **Backend** | [NestJS](https://nestjs.com/) | Framework Node.js robuste |
| **ORM** | [Prisma](https://www.prisma.io/) | Gestion de base de données |
| **Database** | [PostgreSQL](https://www.postgresql.org/) | Base de données relationnelle |
| **Build** | [TypeScript](https://www.typescriptlang.org/) | Superset typé de JavaScript |
| **Linter** | [ESLint](https://eslint.org/) | Analyse de code |

---

## 📝 Notes importantes

- Assurez-vous que PostgreSQL est en cours d'exécution avant de démarrer l'application
- Les migrations Prisma doivent être exécutées après chaque changement du schéma
- Consultez les fichiers README respectifs dans chaque dossier pour plus de détails spécifiques

---