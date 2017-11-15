FROM wordpress

MAINTAINER Truong Vu

# To build source to image, uncomment the following below
# COPY . /var/www/html
# WORKDIR /var/www/html

# Create volume to mount with host directory, for development purpose
# See volumes in docker-compose.yml file
VOLUME ["/var/www/html"]
WORKDIR /var/www/html

# RUN chown -R www-data:www-data .
# RUN chmod 755 -R wp-content/uploads

EXPOSE 80
