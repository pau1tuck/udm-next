# Use the official lightweight Node.js 18 image with Alpine.
# https://hub.docker.com/_/node
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy package.json, package-lock.json (if available) and yarn.lock
COPY package.json yarn.lock ./

# Install Yarn
RUN apk add --no-cache yarn

# Install project dependencies using Yarn
RUN yarn install --frozen-lockfile

# Copy the local code to the container
COPY . .

# Build the Next.js app
RUN yarn build

# Expose the listening port
EXPOSE 3000

# Start the application
CMD ["yarn", "start"]
