# Pulling from Node 6 LTS
FROM node:6

# Make the /src directory
RUN mkdir /src

# Install PM2 globally
RUN npm install pm2@latest -g

# Working directory
WORKDIR /src

# Add the package.json
ADD api/package.json /src/package.json

# Update the main system
RUN apt-get update -y

# Update the PM2
RUN pm2 update

# Install node dependencies
CMD /bin/bash -c 'npm install'

# Expose the port 3000
EXPOSE 3000

# Run the app with forever
CMD pm2-docker app.js -i max --watch
