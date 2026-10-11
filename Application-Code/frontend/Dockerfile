FROM node:21-slim AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

FROM gcr.io/distroless/nodejs:21
WORKDIR /app
COPY --from=build /app /app
EXPOSE 3000
CMD ["npm", "start"]