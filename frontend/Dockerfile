# Use an official Node.js runtime as a parent image
FROM node:lts-alpine AS builder

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the frontend code
COPY . .

# Build the Vue application for production
RUN npm run build

# Use a lightweight web server to serve the static assets
FROM nginx:alpine

# Copy the built Vue app from the builder stage
COPY --from=builder /app/dist /usr/share/nginx/html

# Expose port 80 for the web server
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]