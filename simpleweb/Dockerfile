# Specify a base image

FROM node:alpine

# Specify working directory in container file system
WORKDIR /usr/app 

# Install some dependencies
COPY ./package.json ./
RUN npm install
COPY ./ ./

# Default statup command

CMD ["npm", "start"]