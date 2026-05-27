FROM node:20-alpine

# WORKDIR mirrors the on-disk layout so ../../../../shared resolves correctly
WORKDIR /irctc/user-service

COPY user-service/package*.json ./
RUN npm ci --omit=dev

COPY user-service/prisma ./prisma/
RUN npx prisma generate

COPY user-service/ .
COPY shared/ /irctc/shared/

ENV NODE_ENV=production
EXPOSE 4001
CMD ["npm", "start"]
