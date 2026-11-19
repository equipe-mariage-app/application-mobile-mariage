# Installation et environnement

Le dépôt fournit Docker Compose et une configuration VS Code Dev Containers. La version précise du SDK et la procédure d’installation de la démo Android sont à valider pendant le socle technique.

```bash
git clone https://github.com/Kemadjou-Cabrel/application-mobile-mariage.git
cd application-mobile-mariage
docker compose up -d
docker compose exec flutter-workspace flutter --version
docker compose exec flutter-workspace flutter test
```

Dans VS Code, ouvrir le dossier avec l’extension Dev Containers et choisir « Reopen in Container ». Le navigateur sert à l’aperçu. L’appareil ou l’émulateur Android sert à la démo mobile.

Consulter le [README du dépôt](https://github.com/Kemadjou-Cabrel/application-mobile-mariage#readme) pour le détail des commandes.
