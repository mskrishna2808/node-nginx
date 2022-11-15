FROM node:16.17.1

# COPY index.js .
# COPY package.json .
RUN ls -la
RUN pwd

WORKDIR node-nginx/

RUN ls -la
RUN pwd

COPY . node-nginx/*

RUN ls -la
RUN pwd

RUN npm install

EXPOSE 3000

CMD [ "node", "index.js" ]
