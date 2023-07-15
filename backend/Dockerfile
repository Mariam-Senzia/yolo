#Stage 1
FROM  node:20-slim AS base

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

#stage 2
FROM node:20-slim

COPY --from=base /app /app

WORKDIR /app

EXPOSE 5000

CMD ["npm","start"]
