# Use Node.js image
FROM node:16 AS ionic

# Install Ionic CLI
RUN npm install -g ionic

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN npm install --force --optional

# Copy app source
COPY . .

# Build the app
RUN ionic build

### Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html


