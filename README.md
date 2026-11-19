# 💍 Application Mobile Mariage

## Documentation Sallio

- [Accueil du wiki](docs/wiki/Home.md)
- [Plan de travail et exigences du cours](docs/plan-travail-sallio.md)
- [Backlog des user stories](docs/backlog-sallio.md)
- [Organisation de GitHub Projects et publication du wiki](docs/organisation-github.md)

Bienvenue sur le dépôt du projet de développement mobile ! Ce projet utilise **Flutter** et est entièrement conteneurisé avec **Docker** et **Dev Containers** pour garantir un environnement de développement strict, identique pour tous, et sans conflits de versions.

---

## ⚠️ L'Éditeur Obligatoire : Visual Studio Code

Pour que ce projet fonctionne de manière magique et automatisée, **toute l'équipe doit obligatoirement utiliser Visual Studio Code**. 
Les autres IDE (comme Android Studio ou IntelliJ) ne sauront pas se connecter automatiquement à notre conteneur Docker.

---

## 🚀 1. Prérequis (À installer une seule fois)

Avant de commencer, assurez-vous d'avoir installé les outils suivants sur votre ordinateur :

1. **[Git](https://git-scm.com/)** : Pour télécharger le projet.
2. **[Docker Desktop](https://www.docker.com/products/docker-desktop/)** : Le moteur qui fera tourner notre environnement Flutter. *(Assurez-vous qu'il est allumé et tourne en arrière-plan)*.
3. **[Visual Studio Code](https://code.visualstudio.com/)** : L'éditeur de code de l'équipe.
4. **L'extension VS Code "Dev Containers"** : 
   - Ouvrez VS Code.
   - Allez dans les Extensions (sur la barre de gauche).
   - Cherchez **"Dev Containers"** (par Microsoft) et installez-la.

---

## 🛠️ 2. Démarrage Rapide (Le Workflow de l'équipe)

Vous n'avez **PAS** besoin d'installer Flutter manuellement sur votre machine. Suivez ces étapes :

1. **Cloner le projet :**
   ```bash
   git clone [https://github.com/Kemadjou-Cabrel/application-mobile-mariage.git](https://github.com/Kemadjou-Cabrel/application-mobile-mariage.git)
   cd application-mobile-mariage
   ```

2. **Ouvrir avec VS Code :**
   ```bash
   code .
   ```

3. **Plonger dans le conteneur :**
   Dès l'ouverture, VS Code va détecter notre configuration.
   - Une notification bleue apparaîtra en bas à droite. Cliquez sur **"Reopen in Container"** (Rouvrir dans le conteneur).
   - *Si elle n'apparaît pas : appuyez sur `F1`, tapez "Reopen in Container" et sélectionnez l'option.*
   
   > ☕ **Patientez :** VS Code va automatiquement lancer Docker, construire l'image de Flutter, et installer les extensions nécessaires. Vous saurez que vous êtes à l'intérieur quand un indicateur vert/bleu `Dev Container` apparaîtra en bas à gauche.

---

## 🐳 3. Gestion Avancée du Conteneur Docker (Lancement & Déploiement)

Bien que VS Code gère le conteneur automatiquement pour le développement, vous pouvez avoir besoin de lancer ou déployer l'infrastructure manuellement depuis votre terminal classique (PowerShell / Bash local).

Voici les commandes `docker compose` à exécuter à la racine du projet (là où se trouve le `docker-compose.yml`) :

*   **Construire et lancer le conteneur en arrière-plan (Déploiement) :**
    ```bash
    docker compose up -d --build
    ```
*   **Voir les logs en direct (pour vérifier que tout tourne bien) :**
    ```bash
    docker compose logs -f
    ```
*   **Arrêter le conteneur (sans supprimer les données) :**
    ```bash
    docker compose stop
    ```
*   **Détruire le conteneur (pour tout nettoyer) :**
    ```bash
    docker compose down
    ```
*   **Exécuter une commande Flutter de l'extérieur du conteneur :**
    Si vous n'êtes pas dans VS Code et souhaitez forcer une mise à jour des paquets :
    ```bash
    docker compose exec flutter-workspace flutter pub get
    ```

---

## 💻 4. Comment coder et tester l'application ?

Une fois connecté **dans** le conteneur via VS Code, ouvrez un nouveau terminal intégré (`Ctrl` + `j` ou `` Ctrl + ` ``). C'est un terminal Linux.

*   **Où coder ?** Tout le code source se trouve dans le dossier `lib/`. **Ne codez pas dans le dossier `android/`**.
*   **Mettre à jour les dépendances :**
    Si le fichier `pubspec.yaml` a été modifié :
    ```bash
    flutter pub get
    ```
*   **Tester l'application en direct (Web) :**
    Pour voir l'application, lancez le serveur web Flutter :
    ```bash
    flutter run -d web-server --web-port 8080
    ```
    Ouvrez ensuite votre navigateur et allez à l'adresse : **`http://localhost:8080`**.

---

## 🌿 5. Règle d'or pour Git (Les Branches)

Pour éviter de casser l'application de l'équipe :

1. Ne travaillez **jamais** directement sur `main` ou `develop`.
2. Avant de coder, placez-vous sur la branche principale et mettez-vous à jour :
   ```bash
   git checkout develop
   git pull origin develop
   ```
3. Créez une branche à votre nom pour votre tâche :
   ```bash
   git checkout -b feature/nom-de-la-tache
   ```
4. Une fois terminé, "pushez" votre branche et ouvrez une **Pull Request (PR)** vers `develop`.

---
*Bon code à tous ! 💍*