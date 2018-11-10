FROM node:alpine

WORKDIR /usr/app

# Separe package.json to avoid cache busting
COPY ./package.json ./
RUN npm install

# Separe package.json to avoid cache busting
COPY ./ ./

CMD ["npm", "start"]