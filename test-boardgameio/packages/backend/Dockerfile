FROM node:lts-alpine3.24 AS base

WORKDIR /app

# This Dockerfile expects the build context to be the packages directory.
# Example: docker build -f backend/Dockerfile .
COPY shared ./shared
COPY backend ./backend

WORKDIR /app/backend
RUN npm pkg set dependencies.@project/shared="file:../shared" && npm install

CMD ["npm", "start"]
