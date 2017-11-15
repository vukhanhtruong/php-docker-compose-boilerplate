# Getting Start

## 1. Adjust environment according to your wordpress application
- Download wordpress source code, then extract it
- Open `.env` file, then update wordpress's path to the following variable.

```sh
WORDPRESS_APP_PATH=/path/to/your/project
```

## 2. Setup Wordpress
- For those who need deploy wordpress through ftp, copy all files in `starter-file` to your wordpress folder. On the other hand, just need copy `starter-file/wp-config.php`

- You also can setup wordpress yourself by setting database following the commands below:

```php
/** MySQL database: It need to be matched with `MYSQL_DATABASE` variable in `.env` file */
define('DB_NAME', 'db');

/** MySQL database username */
define('DB_USER', 'root');

/** MySQL database password */
define('DB_PASSWORD', '123456');

/** MySQL hostname */
define('DB_HOST', 'db:3306');
```

## 3. Restore existing database

If you want to restore an existing database, copy your database file into `mysql` folder, then rename it to `db.sql`

## 4. Build/run containers
```sh
docker-compose up -d
```

## 4. Update your system host file (add wordpress.dev)

```bash
sudo echo $(docker network inspect bridge | grep Gateway | grep -o -E '[0-9\.]+') "wordpress.dev" >> /etc/hosts
```

Then, you can access wordpress site with the following links:

- Wordpress site: http://wordpress.dev

- PHPMyAdmin: http://localhost:8080

- Check logs files here: ./logs/apache2

## 5. PHP version

For now, wordpress image is using PHP 5. Let's say you want to work with PHP 7, let check it out [here](https://hub.docker.com/_/wordpress/) first.

Then, open `wordpress/Dockerfile`, modify the first line  from `FROM wordpress` to `FROM wordpress:php7.0`