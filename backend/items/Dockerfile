FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
# Create empty .env file (will be populated later)
RUN touch .env

# Define build-time variables
ARG MONGODB_URI
ARG CLOUD_NAME
ARG CLOUD_API_KEY
ARG CLOUD_API_SECRET
ARG SECRET

# Use them as environment variables at runtime
ENV MONGODB_URI=${MONGODB_URI}
ENV CLOUD_NAME=${CLOUD_NAME}
ENV CLOUD_API_KEY=${CLOUD_API_KEY}
ENV CLOUD_API_SECRET=${CLOUD_API_SECRET}
ENV SECRET=${SECRET}
COPY . .
EXPOSE 3003
CMD ["npm", "start"]