# Use the official PHP 7.4 image as the base image
FROM php:7.4-apache

# Install necessary packages
RUN apt-get update && apt-get install -y \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl gd

# Set the working directory
WORKDIR /var/www/html

# Copy the application files to the container
COPY . /var/www/html

# Set the file permissions
RUN chown -R www-data:www-data /var/www/html

# Expose ports 80, 443 for Apache
EXPOSE 80 443

# Start Apache
CMD ["apache2-foreground"]
