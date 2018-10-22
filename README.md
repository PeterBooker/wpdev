# WPDev
Docker based development environment for WordPress. It includes MySQL(5), Nginx, PHP(7.2) and Memcached.

## Dependencies

* Docker - ([windows](https://docs.docker.com/docker-for-windows/install/), [mac](https://docs.docker.com/docker-for-mac/install/))
* Docker-Compose - ([install](https://docs.docker.com/compose/install/))

## Features

WPDev creates a full development environment for WordPress containing:

[x] - NGINX Web Server
[x] - MySQL Database
[x] - Memcached
[x] - PHP 7.2
[x] - Mail Catcher

You can easily customize this further by editing the `docker-compose.yml` file yourself.

## Usage

This can be used to setup specific sites in their own directory, or included inside a project directory. For the latter, the `docker-compose.yml` can be copied into your project root and the `/.docker/` folder too, you will want to ignore the `/.docker/data/` and `/.docker/wordpress/` folders from version control.

First, clone this repo somewhere temporary:

`git clone https://github.com/PeterBooker/wpdev.git dir-name`

Next, from the newly created directory, start up the Docker containers:

`docker-compose up`

You can remove the containers afterwards with:

`docker-compose down`

You can also remove the containers with:

`docker-compose --rmi=all -v`