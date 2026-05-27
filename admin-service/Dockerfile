FROM node:20-alpine

WORKDIR /irctc/admin-service

COPY admin-service/package*.json ./
RUN npm ci --omit=dev

COPY admin-service/prisma ./prisma/
RUN npx prisma generate

COPY admin-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4003
CMD ["npm", "start"]
