FROM node:16.17.1

# COPY index.js .
# COPY package.json .

WORKDIR /node-nginx

COPY ./../../* node-nginx/

RUN npm install

EXPOSE 3000

CMD [ "node", "index.js" ]
