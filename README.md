# TP FINAL Docker – 21/12/2023
## DUMANOIR David & POIVET Antoine

### Récupération des images Docker

- **Commande utilisée :** `docker pull redis`
  - **Description :** On récupère l'image de la base de donnée Redis pour pouvoir l'utiliser par la suite.

- **Commande utilisée :** `docker pull postgres:15-alpine`
  - **Description :** On récupère l'image de la base de données PostgreSQL version 15 avec une base Alpine pour une installation légère.

### Mise en place du registre local

- **Commande utilisée :** `docker run -d -p 5000:5000 --restart always --name registry registry:2`
  - **Description :** On lance un conteneur Docker nommé "registry" en tant que registre local à l'écoute du port 5000, avec redémarrage automatique, permettant le stockage d'images Docker.

### Stockage des images dans le registre local

- **Commande utilisée :** `docker tag redis:latest localhost:5000/redis:latest`
  - **Description :** On attribue une nouvelle étiquette à l'image Redis, la préparant ainsi pour le stockage dans le registre local à l'adresse localhost:5000.
- **Commande utilisée :** `docker push localhost:5000/redis:latest`
  - **Description :** On pousse l'image Redis étiquetée vers le registre local à l'adresse localhost:5000, la rendant ainsi accessible à d'autres utilisateurs et systèmes.

- **Commande utilisée :** `docker tag postgres:15-alpine localhost:5000/postgres:15-alpine`
  - **Description :** On attribue une nouvelle étiquette à l'image PostgreSQL, la préparant ainsi pour le stockage dans le registre local à l'adresse localhost:5000.
- **Commande utilisée :** `docker push localhost:5000/postgres:15-alpine`
  - **Description :** On pousse l'image PostgreSQL étiquetée vers le registre local à l'adresse localhost:5000, la rendant ainsi accessible à d'autres utilisateurs et systèmes.

### Configuration du projet "humans-best-friend"

- **Commande utilisée :** `git clone https://github.com/pascalito007/ynov-resources.git`
  - **Description :** On clone le dépôt Git contenant les ressources Ynov depuis le lien spécifié.
- **Commande utilisée :** `cd /ynov-resources/2023/m2/dataeng/humans-best-friend`
  - **Description :** On se déplace dans le répertoire spécifié où se trouve le projet "humans-best-friend".

- **Commande utilisée :** `vi docker-compose.build.yml`
  - **Description :** On ouvre l'éditeur de texte Vi pour créer ou éditer le fichier de configuration Docker Compose "docker-compose.build.yml".

- **Commande utilisée :** `vi compose.yml`
  - **Description :** On ouvre l'éditeur de texte Vi pour créer ou éditer le fichier de configuration Docker Compose "compose.yml".

### Déploiement des services Docker

- **Commande utilisée :** `docker compose -f docker-compose.build.yml up -d`
  - **Description :** On lance les services spécifiés dans le fichier Docker Compose "docker-compose.build.yml" en mode détaché.

- **Commande utilisée :** `docker compose up -d`
  - **Description :** On lance les services spécifiés dans le fichier Docker Compose "compose.yml" en mode détaché.

### Démarrage des conteneurs

- **Commande utilisée :** `docker start humans-best-friend-vote-1`
  - **Description :** On démarre le conteneur Docker nommé "humans-best-friend-vote-1".

- **Commande utilisée :** `docker start humans-best-friend-worker-1`
  - **Description :** On démarre le conteneur Docker nommé "humans-best-friend-worker-1".

- **Commande utilisée :** `docker start humans-best-friend-result-1`
  - **Description :** On démarre le conteneur Docker nommé "humans-best-friend-result-1".

### Affichage des conteneurs en cours d'exécution

- **Commande utilisée :** `docker ps`
  - **Description :** On affiche la liste des conteneurs Docker en cours d'exécution.
