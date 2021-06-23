FROM node:13 AS build

WORKDIR /usr/local/app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm install -g @ionic/cli && ionic build --prod

FROM nginx:alpine

COPY --from=build /usr/local/app/www /usr/share/nginx/html

EXPOSE 80
