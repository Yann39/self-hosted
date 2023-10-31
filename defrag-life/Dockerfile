FROM arm64v8/php:8.2-fpm-alpine

LABEL maintainer="Yann39"

# Install mysqli extension
RUN docker-php-ext-install mysqli

RUN addgroup --gid 1000 --system phpuser && \
    adduser --uid 1000 --system phpuser --ingroup phpuser && \
    chown -R phpuser:phpuser /var/www/html && \
    chmod -R 644 /var/www/html

USER 1000

# Start PHP-FPM
CMD ["php-fpm"]