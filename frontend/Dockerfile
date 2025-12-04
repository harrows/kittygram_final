FROM node:18-bullseye AS build

WORKDIR /app

COPY .npmrc ./
COPY package.json package-lock.json ./

RUN npm install

COPY . .

RUN npm run build

FROM node:18-bullseye AS production

WORKDIR /app

COPY --from=build /app/build /app/build

CMD ["bash"]
