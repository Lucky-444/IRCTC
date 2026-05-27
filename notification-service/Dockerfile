FROM node:20-alpine

WORKDIR /irctc/notification-service

COPY notification-service/package*.json ./
RUN npm ci --omit=dev

COPY notification-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4004
CMD ["npm", "start"]
