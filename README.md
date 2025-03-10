# Projet de Documentation

## Description
Ce projet est une API RESTful construite avec Express.js qui fournit une infrastructure backend sécurisée et évolutive. Il comprend des configurations spécifiques à l'environnement (développement/production), une gestion des erreurs, et une prise en charge CORS.

## GitHub Actions Workflow

### Emplacement du workflow
Le workflow CI/CD se trouve dans le fichier `.github/workflows/docker-build.yml`.

### Fonctionnement du workflow
Ce workflow automatise les processus suivants :
- Déclenchement lors des push sur les branches `main` et ainsi que des pull requests vers `main`
- Installation des dépendances Node.js
- Exécution des tests
- Construction de l'image Docker
- Publication de l'image sur GitHub Container Registry (seulement lors des push, pas des pull requests)
- Ajout d'un commentaire sur les pull requests indiquant le statut du build

### Interprétation des résultats
1. Accédez à l'onglet "Actions" sur votre dépôt GitHub
2. Sélectionnez le workflow "Docker Build and Push (CI-CD) auth-app"
3. Vérifiez le statut de chaque run (✅ vert pour succès, ❌ rouge pour échec)
4. Cliquez sur un run spécifique pour voir les détails de chaque étape
5. Pour les pull requests, un commentaire automatique sera ajouté avec le statut
6. En cas de publication réussie, l'image sera disponible à `ghcr.io/[owner]/[repo]/auth-app:latest`