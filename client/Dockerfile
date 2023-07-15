#stage 1
FROM  node:20-slim AS base

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

#stage2
FROM node:20-slim

COPY --from=base /app /app

WORKDIR app/

EXPOSE 3000

CMD ["npm","start"]