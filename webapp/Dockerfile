# Base image node:16
FROM node:16 AS fe-build

# Create custom directory

RUN mkdir /frontend

# Set working directory

WORKDIR /frontend

# Copy the source code to working directory

COPY . /frontend

# Run NPM and DB commands to build the project

RUN npm install
RUN npm run build

# Deploy Nginx for frontend

FROM nginx

# COPY the dist content to nginx HTML folder

COPY --from=fe-build /frontend/dist /usr/share/nginx/html 

