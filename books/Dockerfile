FROM registry.redhat.io/ubi8/ubi

RUN yum --disableplugin=subscription-manager -y install npm && yum --disableplugin=subscription-manager -y install nodejs && yum --disableplugin=subscription-manager clean all

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm cache verify
RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

EXPOSE 8080
CMD [ "node", "server.js" ]
