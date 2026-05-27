FROM node:20-alpine

WORKDIR /irctc/booking-service

COPY booking-service/package*.json ./
RUN npm ci --omit=dev

COPY booking-service/prisma ./prisma/
RUN npx prisma generate

COPY booking-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4005
CMD ["npm", "start"]
