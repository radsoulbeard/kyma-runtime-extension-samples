# build environment
FROM node:current-slim as build
ENV VERSION 1.0.0
WORKDIR /app
COPY frontend-ui5-mssql/package.json ./
RUN npm install
COPY frontend-ui5-mssql/. .
RUN npm run-script build

# production environment
FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
