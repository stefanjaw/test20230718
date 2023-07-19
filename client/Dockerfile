FROM node:20.1 as build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run prod

FROM nginx:1.18
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY --from=build app/dist/angular-tour-of-heroes/ /usr/share/nginx/html

