# WPDev
Docker based development environment for WordPress- Includes Caddy, MariaDB, PHP, Memcached, Mailhog and Adminer.

## Dependencies

* Docker - ([windows](https://docs.docker.com/docker-for-windows/install/), [mac](https://docs.docker.com/docker-for-mac/install/))
* Docker-Compose - ([install](https://docs.docker.com/compose/install/))

## Features

WPDev creates a full development environment for WordPress containing:

- [x] Caddy (Web Server)
- [x] MariaDB
- [x] Memcached
- [x] [PHP](https://github.com/PeterBooker/phpwp) (5.6 / 7.2 / 7.3)
- [x] Mailhog
- [x] Adminer

You can easily customize this further by editing the `docker-compose.yml` file yourself.

## Usage

The easiest way to use this is by cloning it into a directory for each site you want.

`git clone https://github.com/PeterBooker/wpdev.git dir-name`

Next, from the newly created directory, start up the Docker containers:

`docker-compose up -d`

During startup WordPress will be installed if needed. Once running you can access WordPress at `localhost`, Mailhog at `mailhog.localhost` and PHPMyAdmin at `phpmyadmin.localhost`. WordPress files are persisted to `/.docker/wordpress/` and DB files to `/.docker/data/db/`.

From this point you can start and stop the containers with:

`docker-compose start` and `docker-compose stop`

Finally, you can remove the containers:

`docker-compose down`

## TODO

- [ ] Replace Caddy with NGINX and Apache, switched via Environment Variable.
- [ ] Add convenience scripts for DB backups, DB imports and adding content like Theme Unit Test data.

## License

Licensed under MIT.