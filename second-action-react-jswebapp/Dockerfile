# 1. Image de base officielle node (version légère)
FROM node:22-alpine

# 3. Définit le répertoire de travail dans le conteneur
WORKDIR /app

# 4. Copie d'abord uniquement le fichier de dépendances (optimisation du cache Docker)
COPY package*.json .

# 5. Installe les dépendances
RUN npm install

# 6. Copie le reste du code de l'application
COPY . .

RUN npm run build

# 7. Expose le port 8080 sur lequel l'application écoute
EXPOSE 8080

# 8. Commande exécutée au démarrage du conteneur
CMD ["npm", "run", "preview", "--", "--host", "0.0.0.0", "--port", "8080"]