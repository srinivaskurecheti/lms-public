# Docker file nodejs azure app services
FROM node:latest
# Create app directory
WORKDIR /app
# Install app dependencies
COPY package*.json ./
RUN npm install
RUN npm install -g pm2
RUN npx prisma db push
# Build app
COPY . .
RUN npm run build
# Expose port
EXPOSE 8080
# Start app
CMD [ "npm", "start" ]
