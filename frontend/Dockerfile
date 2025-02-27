# Use official Node.js image
FROM node:18-alpine

# Set the working directory for frontend
WORKDIR /app

# Copy the package.json and package-lock.json first
COPY frontend/my-app/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the frontend files
COPY frontend/my-app /app/

# Build the React app
RUN npm run build

# Expose port 3000 for React (development mode) or 80 for production
EXPOSE 3000

# Command to start the app in development mode
CMD ["npm", "start"]
