FROM node:21-slim AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

FROM node:21-alpine
WORKDIR /app
COPY --from=build /app /app
EXPOSE 3500
CMD ["npm", "start"]