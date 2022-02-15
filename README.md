# WPDev
Docker based development environment for WordPress- Includes Caddy, MariaDB, PHP, Memcached, Mailhog and Adminer.

## Dependencies

* Docker - ([windows](https://docs.docker.com/docker-for-windows/install/), [mac](https://docs.docker.com/docker-for-mac/install/))
* Docker-Compose - ([install](https://docs.docker.com/compose/install/))

## Features

WPDev creates a full development environment for WordPress containing:

- [x] NGINX
- [x] MariaDB
- [x] Redis
- [x] [PHP](https://github.com/devilbox/docker-php-fpm) (5.3 / 7.4 / 8.0 / 8.1 / 8.2)
- [x] Mailhog

You can easily customize this further by editing the `docker-compose.yml` file yourself.

## Usage

The easiest way to use this is by cloning it into a directory for each site you want.

`git clone https://github.com/PeterBooker/wpdev.git dir-name`

Next, copy `.env.example` to `.env` and customize the environment variables, adding in the local domain you want to use. Make sure the domain you use is added to your local hosts file.

If you want to use HTTPS then you can overwrite the certs in `.docker/config/certs` with your own (Note: [mkcert](https://github.com/FiloSottile/mkcert) is a great tool.)

Next, from the newly created directory, start up the Docker containers:

`docker-compose up -d`

During startup WordPress will be installed if needed. Once running you can access WordPress at `general.dev` and Mailhog at `mailhog.general.dev`. WordPress files are persisted to `/.docker/wordpress/` and DB files to `/.docker/data/db/`.

If you want to use an existing WordPress repository, you can symlink it into `/.docker/wordpress/`.

Finally, to stop and remove all the containers:

`docker-compose down`

## TODO

- [ ] Add convenience scripts for DB backups, DB imports, adding domains to hosts file and generating SSL certs.

## License

Licensed under MIT.