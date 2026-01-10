FROM node:20-bullseye AS base
WORKDIR /usr/src/app
# Install pnpm
RUN corepack enable && corepack prepare pnpm@10.0.0 --activate

FROM base AS deps
COPY package.json pnpm-lock.yaml ./
RUN pnpm install --frozen-lockfile

FROM base AS builder
ENV NODE_ENV=production
COPY --from=deps /usr/src/app/node_modules ./node_modules
COPY . .
RUN pnpm install --frozen-lockfile --production=false
RUN pnpm run build

FROM node:20-bullseye-slim AS runner
WORKDIR /usr/src/app
ENV NODE_ENV=production
ENV PORT=3000
COPY --from=builder /usr/src/app/dist ./dist
COPY --from=builder /usr/src/app/node_modules ./node_modules
COPY package.json ./package.json

EXPOSE 3000
CMD ["node", "dist/main.js"]
