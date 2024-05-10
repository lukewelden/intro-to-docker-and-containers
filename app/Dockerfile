# Setting base layer as node:10-alpine
FROM node:10-alpine
# Creating a directory for the app
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app
# Setting the working directory
WORKDIR /home/node/app
# Copying the package.json and package-lock.json files
COPY package*.json ./
# Changing the user to node
RUN npm config set registry http://registry.npmjs.org/
# Installing the dependencies
RUN npm install
# Copying the rest of the files
COPY --chown=node:node . .
# Changing the user to node
USER node
# Exposing the port 8080
EXPOSE 8080
# Running the app
CMD ["node", "index.js"]

# To build the image run the following command in your terminal (Make sure you are in the same directory as the Dockerfile)
# docker build . -t node-app
