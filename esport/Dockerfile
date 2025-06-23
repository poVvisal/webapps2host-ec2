FROM nginx:1.25.5-alpine

# Set working directory
WORKDIR /usr/share/nginx/html

# Remove default nginx files
RUN rm -rf ./*

# Copy the HTML file and all supporting files to nginx html directory
COPY index.html ./index.html
COPY "E-Sport Club Management System_files" "./E-Sport Club Management System_files"

# Create a custom nginx configuration (optional)
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80
EXPOSE 80

# Add healthcheck
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
    CMD curl -f http://localhost:80/ || exit 1

# Start nginx (use ENTRYPOINT for better signal handling)
ENTRYPOINT ["nginx", "-g", "daemon off;"]