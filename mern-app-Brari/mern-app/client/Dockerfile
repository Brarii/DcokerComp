# Utiliser l'image de base node:lts-alpine
FROM node:lts-alpine

# Définir le répertoire de travail dans le conteneur
WORKDIR /usr/src/app

# Copier les fichiers package.json et package-lock.json (s'ils existent) dans le répertoire de travail
COPY package*.json ./

# Installer les dépendances avec npm
RUN npm install

# Copier le reste des fichiers du client (le code de l'application React)
COPY . .

# Construire l'application React avec npm run build
RUN npm run build

# Installer un serveur HTTP léger pour servir les fichiers statiques (serve dans ce cas)
RUN npm install -g serve

# Exposer le port 3000 pour l'application
EXPOSE 3000

# Démarrer le serveur pour servir les fichiers construits de React
CMD ["serve", "-s", "build", "-l", "3000"]

