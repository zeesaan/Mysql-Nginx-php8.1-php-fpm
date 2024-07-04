#!/bin/bash

# Update package lists
sudo apt update

# Install Nginx
sudo apt install -y nginx

# Install PHP 8.1 and required extensions
sudo apt install -y software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install -y php8.1-fpm php8.1-mysql php8.1-mbstring php8.1-xml php8.1-gd php8.1-curl php8.1-zip

# Install MySQL 8
export DEBIAN_FRONTEND=noninteractive
sudo apt install -y mysql-server

# Configure MySQL (secure installation)
sudo mysql_secure_installation <<EOF

y
password
password
y
y
y
y
EOF

# Configure PHP-FPM
sudo systemctl start php8.1-fpm
sudo systemctl enable php8.1-fpm

# Clean up
sudo systemctl restart nginx

echo "PHP 8.1 FPM with Nginx and MySQL 8 installation completed."
