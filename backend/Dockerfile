# Use an official Node.js runtime as a parent image
FROM node:lts-alpine

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the backend code
COPY . .

# Expose the port your backend will listen on (e.g., 3000)
EXPOSE 3000

# Start the Node.js application
CMD ["node", "server.js"]