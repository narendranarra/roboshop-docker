FROM node:20-alpine3.21
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop # create roboshop user and group and add roboshop user to roboshop group
WORKDIR /opt/server
RUN chown -R roboshop:roboshop /opt/server
USER roboshop     # every commands run with roboshop user 
COPY package.json .
COPY *.js .
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]  
