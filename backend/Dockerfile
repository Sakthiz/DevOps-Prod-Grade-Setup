#---------------Build Stage----------------

FROM node:18-alpine AS builder 

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

#---------------Ruuntime Stage--------------
    
FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/package*.json ./

ENV NODE_ENV=production

EXPOSE 4657

CMD ["node", "dist/index.js"]
