FROM node:20.13.1-alpine3.19

WORKDIR /21i1123_auth

COPY package*.json ./

RUN npm install

COPY . . 

EXPOSE 4000

CMD [ "node", "index.js" ]