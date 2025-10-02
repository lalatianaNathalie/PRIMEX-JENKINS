FROM node:18-alpine

WORKDIR /app

# Copier package.json et package-lock.json
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Installer nodemon globalement
RUN npm install -g nodemon

# Copier le reste du code
COPY . .

# Exposer le port correct du microservice
EXPOSE 3001

# Démarrer l'application
CMD ["npm", "start"]
