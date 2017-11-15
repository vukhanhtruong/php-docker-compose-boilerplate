# Getting Start

## 1. Adjust .env according to your drupal application

```sh
DRUPAL_APP_PATH=/path/to/your/project
```

## 2. Restore existing database

If you want to restore an existing database, copy your database file into `mysql` folder, then rename it to `db.sql`

## 3. Build/run containers

```bash
docker-compose build
docker-compose up -d
```

## 4. Update your system host file (add drupal.dev)

```bash
sudo echo $(docker network inspect bridge | grep Gateway | grep -o -E '[0-9\.]+') "drupal.dev" >> /etc/hosts
```

## 5. Config database connection

Open settings.php in your drupal folder, then configure similiar like the following command:

```php
$databases = array (
  'default' =>
  array (
    'default' =>
    array (
      'database' => 'drupal',
      'username' => 'drupal',
      'password' => 'drupal',
      'host' => 'db',
      'port' => '',
      'driver' => 'mysql',
      'prefix' => '',
    ),
  ),
);
```

Now, please open your browser then access [drupal.dev](http://drupal.dev)

## 6. Access phpMyadmin

Go to the following URL to access phpMyadmin [localhost:8080](http://localhost:8080)

## 7. Log files

To check the server's log files, open up the folder `logs/nginx`
