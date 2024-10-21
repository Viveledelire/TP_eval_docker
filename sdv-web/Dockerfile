FROM node:23.0.0
WORKDIR /app
COPY ./package*.json ./
RUN npm install
COPY ./app ./app
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]
