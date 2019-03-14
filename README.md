# Drupal 8 - Base image

This image can be used for a custom Drupal 8 environment.

It does not contain any application code, add a Dockerfile to your project with:

```
FROM trimm/drupal-base

# Add application dependencies
COPY --chown=www-data:www-data . /var/www
RUN composer install --no-autoloader --no-progress --no-dev
RUN composer dump-autoload --optimize
```
