FROM node:latest

WORKDIR /app

# Copy package files first for better caching
COPY package*.json ./

# Install dependencies and fix PostCSS + chokidar issues
RUN npm install postcss@8.4.21 postcss-safe-parser@6.0.0 chokidar@3 --legacy-peer-deps
RUN npm install --legacy-peer-deps

# Copy the rest of the application
COPY . .

EXPOSE 3000

# Environment variables
ENV NODE_OPTIONS=--openssl-legacy-provider
ENV PORT=3000
ENV CHOKIDAR_USEPOLLING=true

# Start the React app
CMD ["npm", "start"]

