FROM nginx:alpine

# Install curl for healthcheck
RUN apk --no-cache add curl

# Copy nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]