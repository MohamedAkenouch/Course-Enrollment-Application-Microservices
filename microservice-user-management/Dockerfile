FROM node:12-alpine

#Create app directory 
WORKDIR /usr/src/app

#Copy source code from host to image
COPY package*.json ./

#Install dependencies
RUN npm install --silent

#Bundle app source

COPY . .

#Running port
EXPOSE 3001

ENTRYPOINT [ "npm" , "start" ]