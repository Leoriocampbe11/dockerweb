# Utiliza la imagen base de PHP con Apache
FROM php:7.4-apache

# Copia los archivos del proyecto al directorio raíz de Apache
COPY ./web_personal /var/www/html

# Da permisos al directorio para que Apache pueda acceder a los archivos
RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

# Instala las extensiones de PHP necesarias (como mysqli)
RUN docker-php-ext-install mysqli

# Exponer el puerto 80
EXPOSE 80
