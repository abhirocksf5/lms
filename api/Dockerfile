# Base image node:16
FROM node:16

# Create custom directory

RUN mkdir /backend

# Set working directory

WORKDIR /backend

# Copy the source code to working directory

COPY . /backend

# Run NPM and DB commands to build the project

RUN npm install
RUN npx prisma generate
RUN npx prisma db push
RUN npm run build

# Document which port to use

EXPOSE 8080

# Start the service in backend

CMD ["node","build/index.js"]

