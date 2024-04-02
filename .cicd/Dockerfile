FROM node:14-alpine

# Install git to clone the repository
RUN apk add --no-cache git

# Clone the repository into the container
RUN git clone https://github.com/saipavan168/i27-clothing.git /i27-clothing

# Set the working directory to the cloned repository
WORKDIR /i27-clothing

# Install dependencies
RUN npm install

# Expose port 3000 (assuming your application listens on this port)
EXPOSE 3000

# Define the command to start the application
CMD ["npm", "start"]
