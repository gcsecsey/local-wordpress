# Wordpress setup for local development

I've been using this stack for a while for quick prototyping, debugging and error reproduction on my local machine.

# Prerequisites

- Docker Desktop for Mac and Windows
- Docker Engine and docker-compose for Linux 

# Initialization

## Start fresh instances

Take a look at the compose file, and modify the default credentials and ports if needed. Then start new instances by issuing:

```
docker-compose up -d
```

By default:
- the Wordpress instance will be available on `http://localhost:8080`
- you can connect to the MySQL server on `localhost:3306`

You can stop the instances by running:
```
docker-compose down
```

## PLug existing Wordpress data

- Move the contents of the Wordpress installation into the `src` folder.
- Update `src/wp-config.php` with the MySQL credentials from `docker-compose.yml`

## Plug existing database

Move the contents of the sql dump into the `dump.sql` file. Note that it will be loaded into the database name given to `MYSQL_DATABASE` in `docker-compose.yml`.

## Clearing exisiting instances

> ⚠ Warning
> 
> Note that all data in the MySQL database will be lost

To delete all existing instances, you can run:

```
docker-compose down -v
```

# Tweaks

## Upload limit

The wordpress container's default config allows uploads upto 150MBs. These settings can be adjusted in the `uploads.ini` file.
