# ===== Stage 1 (builder) =====
FROM node:20 AS builder

WORKDIR /app

COPY package.json .
RUN npm install

COPY . .

# ===== Stage 2 (production) =====
FROM node:20-alpine

WORKDIR /app

COPY --from=builder /app /app

EXPOSE 3000

CMD ["node", "server.js"]
