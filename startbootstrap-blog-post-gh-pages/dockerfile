# Use a specific version of Ubuntu Server as the base image
FROM ubuntu:20.04

# Avoid user interaction with tzdata when installing packages
ENV DEBIAN_FRONTEND=noninteractive

# Update package repositories and install NGINX, Python, and pip
# Clean up the apt cache to reduce image size
RUN apt-get update && \
    apt-get install -y nginx

# Set the working directory to the web root
WORKDIR /var/www/html


# Copy the rest of your project
# Ensure that this copy step does not overwrite the Nginx configuration files
COPY . .

# Expose port 80 and 443 for NGINX
EXPOSE 80
EXPOSE 443

# Use exec form of CMD to help NGINX run as PID 1
CMD ["nginx", "-g", "daemon off;"]
