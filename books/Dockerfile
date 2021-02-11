FROM node:14

RUN yum --disableplugin=subscription-manager -y install npm && yum --disableplugin=subscription-manager clean all
RUN mkdir /usr/src/app

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm build

# Bundle app source
COPY . .

EXPOSE 8080
CMD [ "node", "server.js" ]
