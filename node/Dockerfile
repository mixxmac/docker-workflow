FROM node:6-alpine

# Install nodemon
# RUN npm install -g nodemon
# RUN npm install -g pm2

# Install a simple node server
RUN npm install -g httpster

# Provides cached layer for node_modules
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /src && cp -a /tmp/node_modules /src/

# Define working directory
WORKDIR /src
ADD ../dist /src

# Expose port
# EXPOSE 8080

# Expose server default port
EXPOSE 3333

# Run the app using nodemon/pm2
# CMD ["nodemon", "/src/index.js"]

# Run the app using httpster
CMD ["httpster", "dist"]
