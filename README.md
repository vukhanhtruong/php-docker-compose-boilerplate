The customizable docker compose boilerplate for PHP-based projects like Symfony, Drupal, Wordpress.

## Supports:

- Nginx or Apache HTTPd
- PHP-FPM (with Xdebug)
- MySQL, MariaDB
- PhpMyAdmin
- maybe more later...

## Requirements

- GNU/Linux with Docker (recommendation: Vagrant VM with Docker or native Linux with Docker
- [docker-compose](https://github.com/docker/compose)

## Getting Start

```
git clone --recursive https://github.com/vukhanhtruong/php-docker-compose-boilerplate.git projectname

cd projectname

# to show available PHP-based projects
git branch -a

git checkout <branch you want to work on>

# Please check the README.md file in each branch before running the following command
docker-compose up -d
```
