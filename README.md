# WPDev
Docker based development environment for WordPress. It includes MySQL(5), Nginx, PHP(7.2) and Memcached.

## Dependencies

* Docker - ([windows](https://docs.docker.com/docker-for-windows/install/), [mac](https://docs.docker.com/docker-for-mac/install/))
* Docker-Compose - ([install](https://docs.docker.com/compose/install/))

## Features

WPDev creates a full development environment for WordPress containing:

- [x] Caddy Web Server
- [x] MySQL Database
- [x] Memcached
- [x] PHP (5.6 / 7.2 / 7.3)
- [x] Mailhog
- [x] PHPMyAdmin

You can easily customize this further by editing the `docker-compose.yml` file yourself.

## Usage

The easiest way to use this is by cloning it into a directory for each site you want.

`git clone https://github.com/PeterBooker/wpdev.git dir-name`

Next, from the newly created directory, start up the Docker containers:

`docker-compose up -d`

Once running you can access the WordPress site at `localhost`, mailhog at `mailhog.localhost` and phpmyadmin at `phpmyadmin.localhost`.

From this point you can start and stop the containers with:

`docker-compose start` and `docker-compose stop`

Finally, you can remove the containers:

`docker-compose down`

## License

Licensed under MIT.