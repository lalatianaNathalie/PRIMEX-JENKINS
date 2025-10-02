# Étape de build
FROM node:18 AS builder
WORKDIR /app
COPY . .
RUN npm install --legacy-peer-deps
RUN npm run build

# Étape de production
FROM node:18-alpine
WORKDIR /app

# Copie uniquement le build
COPY --from=builder /app ./

# Installe uniquement les dépendances pour la prod
RUN npm install --production --legacy-peer-deps

EXPOSE 3000

CMD ["npm", "start"]
