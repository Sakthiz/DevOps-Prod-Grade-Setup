#--------------- Build Stage --------------

FROM node:18-alpine AS builder

ARG VITE_BACKEND_URL
ENV VITE_BACKEND_URL=$VITE_BACKEND_URL

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN echo "VITE_BACKEND_URL=$VITE_BACKEND_URL" > .env

RUN npm run build

#--------------- Serving Stage --------------

FROM nginx:1.25-alpine

RUN rm -rf /usr/share/nginx/html/*

COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
