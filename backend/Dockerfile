# Use an official Node.js runtime as a parent image
FROM node:18.19.0-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY backend/package*.json ./

# Install dependencies
RUN npm install

# Copy the backend source code
COPY backend/ .

# Expose the port the backend runs on
EXPOSE 5000

# Start the backend application
CMD ["npm", "start"]

