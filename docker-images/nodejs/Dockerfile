FROM node:16.17.1

# COPY index.js .
# COPY package.json .

WORKDIR /node-nginx

RUN pwd
RUN ls -la

RUN cd ~

COPY /home/ec2-user/actions-runner/_work/node-nginx/node-nginx/* /node-nginx/

RUN pwd
RUN ls -la

RUN npm install

EXPOSE 3000

CMD [ "node", "index.js" ]
