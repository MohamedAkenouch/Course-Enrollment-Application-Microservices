# Stage 1: compile angular frontend
FROM node:12-alpine as build-step

#Create app directory 
RUN mkdir -p /app

#Working dir
WORKDIR /app

COPY package.json /app

RUN npm install --silent

COPY . /app

RUN npm run build --prod

RUN ls -al /app

# Stage 2: serve app with nginx server
FROM nginx:1.17.1-alpine

COPY --from=build-step /app/dist/client-side /usr/share/nginx/html

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

