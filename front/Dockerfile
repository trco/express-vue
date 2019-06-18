FROM node:11-alpine

WORKDIR /front

COPY package.json ./

RUN npm install

EXPOSE 8080

CMD [ "npm", "run", "serve" ]
