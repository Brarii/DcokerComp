# Étape 1 : Utiliser l'image de base Node.js LTS Alpine
FROM node:lts-alpine

# Étape 2 : Définir le répertoire de travail dans le conteneur
WORKDIR /usr/src/app

# Étape 3 : Copier les fichiers package.json et package-lock.json (ou yarn.lock)
COPY package*.json ./

# Étape 4 : Installer les dépendances avec npm
RUN npm install

# Étape 5 : Copier le reste des fichiers du serveur dans le conteneur
COPY . .

# Étape 6 : Exposer le port 9000
EXPOSE 9000

# Étape 7 : Définir la variable d'environnement MONGO_URI
# Cette variable sera définie dans le fichier Docker Compose
# ENV MONGO_URI=${MONGO_URI}

# Étape 8 : Démarrer l'application avec npm start
CMD ["npm", "start"]

