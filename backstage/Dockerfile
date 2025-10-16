# Dockerfile
FROM node:20-bookworm-slim

# Install dependencies
RUN apt-get update && apt-get install -y git python3 make g++ && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app/backstage

# Copy your local code into the image
COPY . /app/

# Enable Yarn via corepack
RUN corepack enable

# Install dependencies
RUN yarn install --frozen-lockfile

# Expose ports
EXPOSE 3000 7007

# Set environment vars
ENV NODE_ENV=development
ENV NODE_OPTIONS=--no-node-snapshot

# Automatically start Backstage
CMD ["yarn", "start"]
