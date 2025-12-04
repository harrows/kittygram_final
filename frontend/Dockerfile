FROM node:18-bullseye as build

WORKDIR /app

# Используем зеркало npm
COPY .npmrc ./

# Копируем файлы зависимостей
COPY package.json package-lock.json ./

RUN npm install

COPY . .

RUN npm run build
