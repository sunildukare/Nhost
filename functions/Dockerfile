# Use an official Node.js runtime as a parent image
FROM node:18

# Set the working directory
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Install TypeScript
RUN npm install -g typescript

# Copy the function code
COPY sub ./sub

# Compile TypeScript to JavaScript
RUN tsc sub/hello.ts --outDir sub

# Set the command to run your function
CMD [ "node", "sub/hello.js" ]

# Expose the port the app runs on
EXPOSE 8080
