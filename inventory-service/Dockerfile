FROM node:20-alpine

WORKDIR /irctc/inventory-service

COPY inventory-service/package*.json ./
RUN npm ci --omit=dev

COPY inventory-service/prisma ./prisma/
RUN npx prisma generate

COPY inventory-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4007
CMD ["npm", "start"]
