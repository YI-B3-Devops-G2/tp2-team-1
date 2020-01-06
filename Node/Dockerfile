FROM node:lts-alpine

ENV API_PORT 4040

# Create app directory
WORKDIR /home/node/app
RUN chown -R node:node /home/node/app
USER node

COPY package.json /home/node/app
RUN npm install
COPY . /home/node/app

# Commands at runtime
# Command "dev" does not work
CMD [ "npm", "run", "start" ]

EXPOSE 4040