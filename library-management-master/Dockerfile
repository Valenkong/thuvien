FROM php:8.2-apache

# Cài driver cần thiết cho PHP
RUN docker-php-ext-install pdo pdo_mysql mysqli

# Thêm ServerName để tránh cảnh báo khi khởi động Apache
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

# Copy source code vào container
COPY . /var/www/html/

# (Tuỳ chọn) cấp quyền nếu cần
RUN chown -R www-data:www-data /var/www/html

# Mở cổng 80
EXPOSE 80
