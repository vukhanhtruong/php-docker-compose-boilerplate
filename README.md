
# Getting Start

## 1. Adjust .env according to your symfony application

```sh
SYMFONY_APP_PATH=/path/to/your/project
```

## 2. Restore existing database

If you want to restore an existing database, copy your database file into `mysql` folder, then rename it to `db.sql`

## 3. Build/run containers

```bash
docker-compose build
docker-compose up -d
```

## 4. Update your system host file

```bash
sudo echo $(docker network inspect bridge | grep Gateway | grep -o -E '[0-9\.]+') "symfony.dev" >> /etc/hosts
```

## 5. Prepare Symfony app
1. Update app/config/parameters.yml match with following content:

```yml
# path/to/your/symfony-project/app/config/parameters.yml

database_host: db
database_database_name: symfony
database_user: symfony
database_password: symfony
```

2. Composer install & create database

```bash
$ docker-compose exec php bash
$ composer install
$ sf doctrine:database:create
$ sf doctrine:schema:update --force
```

## 5. Access phpMyadmin

Go to the following URL to access phpMyadmin [localhost:8080](http://localhost:8080)

## 6. Log files

To check the server's log files, open up the folder `logs`
