# Use an official Node.js runtime as a parent image
FROM node:18.19.0-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY frontend/package*.json ./

# Install dependencies
RUN npm install

# Copy the frontend source code
COPY frontend/ .

# Build the frontend application
RUN npm run build

# Use an Nginx image to serve the built frontend
FROM nginx:alpine
COPY --from=0 /app/build /usr/share/nginx/html

# Expose the port the frontend runs on
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
