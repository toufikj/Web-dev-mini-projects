FROM node:18

# Set the working directory
WORKDIR /usr/src/app

# Install dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Update Browserslist database
RUN npx browserslist@latest --update-db

# Set the environment variable
ENV NODE_OPTIONS=--openssl-legacy-provider

# Build the React application
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]

