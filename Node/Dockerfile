FROM node:lts-alpine

ENV API_PORT 3000

# Create app directory
WORKDIR /home/node/app
RUN chown -R node:node /home/node/app
USER node

COPY package*.json ./
COPY . .

# Commands at runtime
# Command "dev" does not work
CMD [ "ls", "npm", "run", "start" ]