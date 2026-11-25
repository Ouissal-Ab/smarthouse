# Étape 1 : compiler Angular
FROM node:14.15.0-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Étape 2 : servir avec Nginx
FROM nginx:alpine
COPY --from=builder /app/dist/smart-home /usr/share/nginx/html
