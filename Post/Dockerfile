FROM node:20.13.1-alpine3.19

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . . 

EXPOSE 4002

CMD [ "node", "index.js" ]