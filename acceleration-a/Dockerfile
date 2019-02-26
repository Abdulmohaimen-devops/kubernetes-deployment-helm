# This Docker image uses the latest version of  Node 
# and uses Docker multistage builds

# Use node for the build stage
FROM node as builder

# Copy application source code to /app directory
# of  your container
COPY . /app

# The application's directory will be the working directory
WORKDIR /app

# setup all required components
RUN yarn install

# build production ready code
RUN yarn build

# Use node  for the target image
FROM node

# Copy the application and installed modules from the previous build stage
COPY --from=builder /app /app

# The application's directory will be the working directory
WORKDIR /app

#set ENV value to run app 
ENV WEB_PORT 3002

# Run your app!
CMD  yarn start 