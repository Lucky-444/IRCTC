FROM node:20-alpine

WORKDIR /irctc/search-service

COPY search-service/package*.json ./
RUN npm ci --omit=dev

COPY search-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4002
CMD ["npm", "start"]
