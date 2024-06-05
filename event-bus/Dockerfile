FROM node:20.13.1-alpine3.19

WORKDIR /21i1123_eventbus

COPY package*.json ./

RUN npm install

COPY . . 

EXPOSE 4009

CMD [ "node", "index.js" ]