# First Stage
FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json ./
COPY server.js ./

RUN npm install


# Final Stage
FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app/node_modules /app/node_modules

COPY . .

EXPOSE 3000

CMD ["node", "server.js"]
