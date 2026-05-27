FROM node:20-alpine

WORKDIR /irctc/payment-service

COPY payment-service/package*.json ./
RUN npm ci --omit=dev

COPY payment-service/prisma ./prisma/
RUN npx prisma generate

COPY payment-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4006
CMD ["npm", "start"]
